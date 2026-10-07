---
apple-notes-id: EFC27146-4FE7-4AF5-9FDD-D7AA45AD47F9
---
Compensacão tributaria
https://apple.ent.box.com/file/1449880338437?s=sasu0xkrn3oz1h74tnr8c8mrvnwe482p


### Soluções propostas 
1. Solução baseada em euristica
	- Check if the values reported in the XLS tables are present in the processed document
1. Solução baseada em ML
	- Ask questions to your documents with Retrieval Augumented Generation(RAG)

### Software Suite

1. Execution Shell Script
1. Desktop Application
2. Web Application

——
### Summary
A solução a ser desenvolvida constitui-se de uma aplicação de Inteligência Artificial capaz de comparar a cobrança versus documentação, objetivando realizar 100% de auditoria nos processos. Dado os exemplos apresentadas, comprovou-se a necessidade de uma ferramenta de OCR acoplada a solução de comparação.

> 📗 **Background**
> FoxCom trabalha com a planilha Tooling claim: 
- Planilha que lista todos os valores específicos associados a cada item, com abas específicas. Consta com Abas que reportam vários detalhes como itens comprados, transferidos, Fretes, Custos e impostos. Etc.

> **Problema:**
- Há uma extensa informação dos itens que sofrem auditoria.
- A Checagem acontece despesa a despesa, processo a processo. Listam-se as despesas. Abre-se arquivo a arquivo pra identificar a despesa.
- Apple seleciona a quantidade de processos que dão 85% do valor a ser reembolsado pela FoxCom.
- Os documentos e imagens utilizados como evidências dos pagamentos não possuem um formato padrão.
- Parte significativa dos documentos são imagens
> Principal pergunta a ser respondida pela solução a ser desenvolvida:
- Nota fiscal emitida corresponde ao valor que foi lançado na planilha?

> ✅ **Requirements**
- Dicionário de documentos:
	- Fornecedores que produzem esses documentos
- Amostragem representativa de tipos de documentos for fonte de despesa (colunas da tabela apresentada)

> ⚠️ **Risks**
1. Atenção à LGPD

> 🎯 **Ações:**
> 1. Enviar Lista de pessoas para compor NDA (DRIs: Gabriela Costa e Professor Serra)
> 2. Enviar NDA (DRI: Vianna)
> 3. Enviar dúvidas e requisitos técnicos para Vianna (DRI: Claudio Fortier)
> 4. Enviar ata de reunião e gravação (DRI: Vianna)