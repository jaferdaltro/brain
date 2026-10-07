---
apple-notes-id: 2071C48E-7D84-46DE-B458-1B8CABD8E8E0
---
#recon #trainnig 

### Unit Store
Feature flag

Essa tela mostra a visão geral de todas as unidades que o projeto tem para serem testadas

![[Pasted Graphic 26.png]]

Em build config consigo ver qual o tipo de material o dispositivo foi construído.
Ex: se a tela é de plástico ou vidro.

UNIT_NUMBER é um alias para o SERIAL NUMBER 

EVENTO - WATERFALL 
LTOS - LONG TERM OPERATIONAL STRESS
FA-TICKET - FAIL ANALISES TICKET 
O ciclo de **FA ANALISES** inicia logo após um ciclo de testes. 
Ex: sn1 -> drop1 -> drop2-> drop3-> (x) —
																-> FA ANALYSIS
																							-> drop4

FAIL STOP

COF - carry-on fail
Despite failing tests, units continue to flow down testing line to collect data. Also continue-on fail.

RECON - SETUP 
- SERIAL NUMBER DAS UNIDADES TESTADAS (SERIAL NUMBERS)
- QUAIS TESTES SERÃO FEITOS (**WATERFALL TEST PLAN** E **REL EVENT CHEC**K)
- ERROS QUE SERÃO TRAQUEADOS (FAILURE MODES)

COMO MANDAR OS ERROS
- VIA INSIGHT (DADOS DE PROJETOS)
	- CONEXÃO COM INSIGHT PARA OBTER DADOS
	- DATA SOURCES

- &nbsp;

![[Pasted Graphic 1 12.png]]

		AUTOMATIZANDO O RECEBIMENTO DOS DADOS VIA INSIGHT 
	

![[Pasted Graphic 2 9.png]]


- VIA RADAR
	- UPLOAD DE CSV
- VIA MANUAL
	- INSERINDO OS CSV