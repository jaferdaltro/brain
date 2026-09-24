After switching the language to ar_AR, the content for ErrorSerialNum is displayed in reverse order


Erro no idioma Árabe
chave inputs::serial-number::error

A chave reportada na issue é `ErrorSerialNum`  porém a chave usada no código é `error` apresentada no json abaixo.
```
"inputs":{
	"serial-number": {
		"error": "أدخل رقمًا تسلسليًا من 6-18 حرفًا، يحتوي عل حرف \"-\" واحد فقط" 
	}
}
```

LOKALISE 

https://app.lokalise.com/project/77286895669e834b319fe2.15304992/?view=multi&search=inputs::serial-number::error
![[Pasted image 20250822084618.png]]

https://app.lokalise.com/project/77286895669e834b319fe2.15304992/?view=multi&k=606794955&search=key::sections::search-devices::supportiveText::isErrorInSerialNum
![[Pasted image 20250821100223.png]]


Resposta do chat GPT
![[Pasted image 20250821095842.png]]
EXATAMENTE COMO ESTÁ NO CÓDIGO


Google Tradutor
![[Pasted image 20250821101744.png]]

Me parece que está correto.


idoia.subinas@hp.com

---
HPXAPPS-42095 - [PPR] Add Device HP Smart Header Text Horizontal Margin
https://hp-jira.external.hp.com/browse/HPXAPPS-42095

Adicione um texto do cabeçalho da impressora e falta um texto do cabeçalho do dispositivo deve ser 24px do lado esquerdo

 "@clientos/ui-toolkit": "2.0.5"

O problema está nos componentes de GenericCard do ui-toolkit

![[Pasted image 20250822161506.png]]

![[Pasted image 20250822161548.png]]
![[Pasted image 20250822161811.png]]
