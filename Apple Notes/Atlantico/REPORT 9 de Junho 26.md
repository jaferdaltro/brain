---
apple-notes-id: B0F65BF0-89E0-47F9-A16D-C7F11B1B7741
---
#report #hp #atlantico 

## SYNC INTERNA
- PROTEC sempre vai ser duplo
- Avaliação de desempenho
	- Dar uma olhada no Calendário do Ciclo de Avaliação 
	- Prioridade em 3 treinamentos
		- Politica de Qualidade
		- Programa de Integridade
		- Segurança da Informação

## HORIZ-2533 - **CANCELED**  
#bug 
[**https://hp-jira.external.hp.com/browse/HORIZ-2533**](https://hp-jira.external.hp.com/browse/HORIZ-2533)

> Ao logar na conta [**testqa.moqa.daisy+0529pa@outlook.com**](mailto:testqa.moqa.daisy+0529pa@outlook.com) a printer é recebida pela d**igital-services-northbound-api**, entretanto o status code da printer vinculada a essa subscription é de ‘EXCEPTION’. Como podemos ver no screenshot.

> No status mapping da **Digital Services Northbound API** não temos este estado para que o tracking card possa ser exibido.



> When logging into the account **testqa.moqa.daisy+0529pa@outlook.com**, the printer is received by the **digital-services-northbound-api**. However, the status code of the printer associated with this subscription is **“EXCEPTION”**, as shown in the screenshot.
> In the **Digital Services Northbound API** status mapping, this state does not exist, which prevents the tracking card from being displayed.


A baixo está o histórico dos estados em que a subscription passou:


```
{
  "subscriptions": [
    {
      "tenantId": "27fd382a-4eaa-42ca-854d-887451ade717",
      "type": "HP_ALL_IN",
      "tracking": [
        {
          "type": "PRINTER",
          "entity": {
            "sku": null,
            "type": "PRINTER",
            "serialNumber": "TH65D28028",
            "uuid": "d7d30dff-c951-4d44-a829-2f57288637a2",
            "modelName": null,
            "association": "pending"
          },
          "state": {
            "code": "EXCEPTION",
            "progression": [
              {
                "at": "2026-05-29T06:50:42.000Z",
                "code_event": "invoiced",
                "links": []
              },
              {
                "at": "2026-05-29T06:48:58.000Z",
                "code_event": "shipped",
                "links": [
                  {
                    "type": "TRACKING",
                    "data": "https://www.fedex.com/fedextrack/?tracknumbers=391827834"
                  }
                ]
              },
              {
                "at": "2026-05-29T06:48:27.000Z",
                "code_event": "processing",
                "links": []
              },
              {
                "at": "2026-05-29T02:10:32.000Z",
                "code_event": "received",
                "links": []
              },
              {
                "at": "2026-05-29T02:11:57.000Z",
                "code_event": "new",
                "links": []
              }
            ]
          },
          "order": {
            "id": "121995885",
            "status": "INVOICED"
          },
          "links": [
            {
              "type": "TRACKING",
              "data": "https://www.fedex.com/fedextrack/?tracknumbers=391827834"
            }
          ]
        }
      ]
    }
  ]
}
```

Os estados de tracking foram:
- new
-received
-processing
-shipped
-invoiced

—
Sprint Atual:
2026Q3.3
Prox.:
2026Q3.4