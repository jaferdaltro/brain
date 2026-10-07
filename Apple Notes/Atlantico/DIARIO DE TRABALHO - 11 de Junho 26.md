---
apple-notes-id: ED8D79E3-4FC1-4D5A-AF49-A756277F90A4
---
#report #hp #atlantico 


## Treinamento Obrigatório - Programa de Integridade
Lei Anticorrupção Decreto Presidencial 8.429 de março de 2015
Processos e auditorias 
- Fase 1 - Iniciar
	- Código de Conduta
- Fase 2 - Planejar
	- Comitê de Ética: Composto pelos colaboradores indicados pelo corpo gerencial e superintendente

![[Pasted Graphic 38.png]]

- Fase 3 - Executar e Monitorar
	- Estabelecer e manter um canal de tranparênia
- Fase 4 - Avaliar
- Fase 5 - Finalizar
- Código de Conduta
	- Valores:
		- Excelência
		- Colaboração
		- Ética
		- Valorização das pessoas 
		- Inovação

## HORIZ-1664 - ANALYTICS
https://hp-jira.external.hp.com/browse/HORIZ-1664
#kibana #analytics 

- **Expected Result**
	Only one viewDisplayed event should be generated per Device List screen view.
- **Actual Result**
	Multiple viewDisplayed events are generated for a single Device List screen view in Kibana.


- Múltiplos **viewDisplayed** events
- viewDisplayed event entries generated for the same screen render.
- how to prevent duplicate events: https://shiny-lamp-gz32e6g.pages.github.io/windows/guides/enabling_analytics_on_MFEs_guide/#important-preventing-duplicate-events 
O problema acontece na print-mfe, existe uma duplicação no evento de viewDisplayed, me parece que o mãe de cep tá trazendo o mesmo log.

### Mac - printer 

```
action: "ViewDisplayed"
actionAuxParams: "taxonomyName=UNI_PF:IIN_PR:PRO_GetSuppliesDefault_GetSupplies Default"
controlAuxParams: "FriendlyName=Get Supplies default"
controlLabel: "GetSuppliesDefault"
controlName: "GetSuppliesDefault"
version: "2.0.0"
viewHierarchy: ["base:/", "mfe:/Print/GetSuppliesDefault/"] (2)
viewMode: "HpxSuppliesTile"
viewModule: "Print"
viewName: "GetSuppliesDefault"
```

testqa.moqa.daisy+0529pa@outlook.com
Aio1test

26.3.0.3885
- REMOVER AS CONFIGURAÇÕES DO HPX NO MAC
	- ~/Library/Containers/com.hp.SmartMac