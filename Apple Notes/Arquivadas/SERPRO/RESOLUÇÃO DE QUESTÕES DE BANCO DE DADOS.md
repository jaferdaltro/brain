---
apple-notes-id: 5DF56A5D-CF03-409F-896A-0048A31EC333
---
4.3. Nível de Paralelismo em Consultas Para se obter um melhor desempenho, no caso de consultas, para sistemas paralelos pode-se obter o paralelismo em duas formas, descritas a seguir.
4.3.1. Paralelismo entre consultas De acordo com Korth, H. (1999, p. 571), o paralelismo entre consultas é a forma de paralelismo mais fácil de manter em um sistema de banco de dados, principalmente em um sistema paralelo de memória compartilhada. Sua principal aplicação é melhorar o sistema de processamento de transações de modo a aceitar um número maior de transações processadas por segundo. Consiste em executar consultas ou transações distintas em paralelo umas com as outras.
4.3.2. Paralelismo interno a consulta Uma única consulta é executada paralelamente em diversos processadores e discos. Segundo Korth, H. (1999, p. 572), isto é importante para melhorar o tempo de execução de consultas com grande tempo de duração, pois pode-se paralelizar as operações relacionais sobre diferentes conjuntos de relações existentes. Meyer, L. (1997, p. 27) descreve que este tipo de paralelismo “(...) consiste da execução paralela de diferentes operadores dentro de uma única consulta. Se um operador pode enviar o resultado obtido para o seguinte, ambos podem executar em paralelo, diminuindo o tempo de resposta da consulta”. Este paralelismo pode ser canalizado (pipeline) ou independente. Na canalização, por exemplo, as tuplas resultantes em A serão utilizadas para a computação em B (como em uma linha de produção). No caso da independência, por exemplo, A e B não possuem uma dependência para se obter um resultado final de uma operação entre eles, como acontece no pipeline. Apesar da utilização do pipeline em um sistema paralelo, a princípio, ter a mesma finalidade de utilização em um sistema seqüencial, Korth, H.(1999, p.582) diz que pode-se extrair o paralelismo no pipeline, da mesma forma que os canais de instrução são usados como uma das fontes de paralelismo em um projeto de hardware. Como exemplo de paralelismo pipeline, considere uma junção entre três conjuntos de relações (r1, r2 e r3). O processamento da junção de r1 com r2 será efetuado por A. B computará a junção do resultado de A com r3. O paralelismo será obtido ao passo que as 24 tuplas já computadas em A estarão sendo enviadas a B para a computação com r3 sem que A tenha terminado completamente a operação de junção entre r1 e r2

Quanto mais fina a granulosidade, mais preciso o bloqueio pode ser, e mais paralelismo pode ser obtido. Quando mais fina a granularidade, maior será o número de bloqueios, aumentando portanto, o overhead(custos) de gerenciamento de bloqueios

Quanto maior a granulosidade, menor o overhead(custos) para aquisição e liberação de bloqueios, porém usualmente serão bloqueados mais dados do que a transação precisa, diminuindo a concorrência.

Os bloqueios são gerenciáveis (podem sofrer alterações). Porém, o custo desse gerenciamento varia conforme o grau de granularidade.

## Balanceamento de carga e conceitos de falhas e recuperação

O que é?
Caso alguma falha ocorra em um banco de dados, é preciso garantir que ele volte ao seu estado consistente, ou seja, atualizações devem ser desfeitas ou refeitas. Entretanto, existe uma técnica que não necessita realizar o UNDO ou o REDO de suas alterações. Conhecida também como técnica NO-REDO ou NO-UNDO, a técnica **shadow paging** (paginação em sombra) baseia-se na existência de uma <u>tabela de blocos</u> (páginas) de disco. 

**A paginação em sombra** considera que o BD é composto por um número de páginas de tamanho fixo (ou bloco de discos) para processo de recuperação. Um catálogo com n entradas é construído no qual a i-ésima entrada aponta para a i-ésima página do BD em disco. Se não for muito grande, o catálogo será mantido na memória principal. 

Na transação, o catálogo corrente, cujas entradas apontam para os mais recentes ou correntes páginas em disco é copiado em um shadow (sombra), o qual é salvo no disco, enquanto o catálogo corrente é usado pela transação.
Durante a execução da transação, o catálogo shadow nunca é modificado.

Ex: A operação escrever_item for executada, uma nova cópia da página modificada do BD será escrita, mas a cópia antiga dessa página não será sobrescrita. Para recuperar, basta livrar-se das páginas modificadas e descartar o catálogo corrente.

Vantagens:
-adequada a SGBD monousuário
-sem overhead de escrita dos registros de log
-recuperação é trivial

Desvantagens
-gerenciamento complexo em SGBD multiusuário
- os dados podem estar fragmentados no disco
-requer coleta de lixo: quando encerra, existem páginas obsoletas

Fonte: Youtube, Paginação em Sombra - Carlos Eduardo e Marcos Gilmário.

## METADADOS
Segundo Silberschatz \[1\], o SGDB deve armazenar, além dos dados, um conjunto de **metadados**, chamado de **catálogo** ou **dicionário**. Alguns exemplos de metadados armazenados pelos SGDBs são:
- Informações sobre as relações:
	- Nome das tabelas
	- Nome dos atributos
	- Domínios e tamanho dos atributos
	- Restrições de integridade
- Informações sobre usuários:
	- Nomes dos usuários
	- Senhas
	- Permissões
- Estatísticas e informações para otimização das atividades:
	- Número de tuplas em cada relação
	- Método de armazenamento
	- Nomes e tipos de índices


#db #tecnologia