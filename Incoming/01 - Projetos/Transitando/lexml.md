## Como funciona a API do LexML

O LexML expõe um serviço de busca no padrão **SRU** (Search/Retrieval via URL), definido originalmente pela Library of Congress — é um protocolo REST simples, baseado em GET, que retorna XML. A API permite realizar pesquisas por meio de URLs e receber o resultado no formato XML, seguindo o padrão SRU.

**Endpoint oficial:**

```
https://www.lexml.gov.br/busca/SRU
```

**Parâmetros principais:**

- `operation=searchRetrieve`
- `query=` — expressão em CQL (Common Query Language)
- `maximumRecords=` — quantidade de resultados (até 100)
- `startRecord=` — paginação
- `recordSchema=dc` (Dublin Core) ou `oai_dc`

**Exemplo de query CQL para resoluções do CONTRAN:**

```
autoridade="contran"
```

ou combinando com tipo de documento:

```
autoridade="contran" and tipoDocumento="Resolução"
```

⚠️ Nota técnica: tentei buscar diretamente esse endpoint agora e o robots.txt do site bloqueou o acesso automatizado por aqui (minha ferramenta de busca respeita robots.txt). Isso não significa que a API esteja indisponível — só que eu, neste momento, não consigo testá-la ao vivo. Meu código/backend, rodando fora dessas restrições, deve conseguir consumi-la normalmente, mas vale você mesmo testar num navegador ou Postman antes de programar a integração.

## O que o retorno traz

Cada resultado no XML retorna metadados estruturados como:

- `<urn>` — o identificador persistente único do documento
- `<dc:title>` — título (ex.: "Resolução CONTRAN nº 985, de 15 de dezembro de 2022")
- `<dc:date>` — data
- `<dc:description>` — ementa
- `<autoridade>` — órgão emissor
- `<tipoDocumento>` — tipo de ato
- `<localidade>` — jurisdição

## O identificador URN (chave para versionamento)

Um diferencial importante do LexML é o **URN persistente**, que segue uma gramática própria (ex.: `urn:lex:br:federal:lei:1990-09-11;8078`). Isso permite:

- referenciar uma norma de forma estável mesmo que o link mude;
- resolver a URN para a URL atual via um resolvedor: `https://www.lexml.gov.br/urn/{urn}`;
- rastrear **versões e alterações no tempo** de uma mesma norma (o modelo prevê elementos de "versão" e "visão" — ou seja, dá pra saber quando uma Resolução CONTRAN foi alterada por outra, e recuperar o histórico).

Isso é particularmente valioso para o seu caso: como o MBFT é alterado por resoluções avulsas (985/2022 → 1.003/2023 → 1.009/2024 → 1.012/2024...), o LexML te dá uma forma programática de rastrear essa cadeia de alterações, ao invés de caçar cada resolução manualmente no DOU.

## Limitação importante

O LexML indexa **metadados e aponta para a fonte** (geralmente o link do documento no site de origem, como Diário Oficial/Imprensa Nacional), mas nem sempre entrega o **texto integral estruturado em XML** — isso depende de o órgão emissor (no caso, o CONTRAN/Ministério dos Transportes) ter enviado o documento como "provedor de dados" no formato XML do LexML. Resoluções do CONTRAN, na prática, costumam estar disponíveis como PDF vinculado. Então:

- **Para descoberta e indexação das resoluções (título, data, ementa, link)**: o LexML resolve bem.
- **Para extrair o texto/fichas do MBFT** de forma estruturada (artigo por artigo, código de infração por código de infração): você provavelmente ainda vai precisar de parsing de PDF por cima, porque o Manual em si não é publicado como documento articulado em XML no LexML.

## Existem wrappers prontos

Encontrei dois exemplos que confirmam a viabilidade prática:

- Um **wrapper Python** (`py-lexml-acervo`) que já implementa consultas SRU e parsing do XML de retorno.
- Servidores **MCP** (`LeXML-mcp`, `mcp-juridico-brasil`) que expõem ferramentas de busca e resolução de URN sobre essa mesma API — sinal de que a integração é suficientemente estável para esse tipo de uso.

**Resumo da arquitetura recomendada para seu caso:**

1. **LexML/SRU** → catálogo e histórico de Resoluções CONTRAN (metadados, URN, links, cadeia de alterações).
2. **Parsing de PDF** (das próprias resoluções e do MBFT) → extração das fichas de infração.
3. Usar a **URN do LexML** como chave de referência cruzada entre a ficha do manual e a resolução que a originou/alterou.

Quer que eu monte um protótipo de chamada à API (endpoint, query CQL de exemplo e parsing do XML) para você testar a integração?