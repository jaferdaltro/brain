## No values are seen for actionAuxParams and controlAuxParams in Device List for onLoad and onClick.

WIN v50.52545.10994.0

**Repro steps:**

1. Install and launch the app.
2. On the Common Consents screen select "Accept All".
3. click on continue as guest.
4. Click on Primary card, secondary card, dock card, pen card, print card.
5. Open external browser and navigate to Kibana. 
6. Enter serial number:5CD4521220
7. Check the actionAuxParams and controlAuxParams for onLoad and onClick respectively.

**Expected result:** 

1. actionAuxParams field should have (ie – TotalDeviceCt=, TotalPrinterCt=, etc) and  controlAuxParams field should have field (ie- Device Type=, (devicetype)&CardIndex=…)

**Actual result:** 

1. actionAuxParams and controlAuxParams for onLoad and onClick are not showing any values.

## SOLUÇÃO
PASSADO PARA O TIME DE INSTRUMENTATION (Daniel Coelho)