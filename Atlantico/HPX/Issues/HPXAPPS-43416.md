 The name of '我的电脑' changed to 'My Computer' after return to the Devices page on the AB2_ZH image.
https://hp-jira.external.hp.com/browse/HPXAPPS-43416 
VERSÃO DO BUG
48.52533.6679.0_REBRAND_PROD
**Steps to Reproduce:**  
1. GM dash build 23WW6IDZ6ac#SAB2#DAB2 successfully. Go through OOBE with ZH language and boot into DT.  
2. Connect to the network->Launch HPX from all apps.  
3. Click on Main page and go to Devices page.  
4. Click Audio button on Devices page-->Click back button to the Devices page.  
5. Found the '????' change to 'My Computer'.  
6. So issue occurred.

1 TESTE  V.181
```
   "zh": [
          "cn"
        ]

```
2 TESTE V.48.52533.6679

Filtro de Bugs 
[Issue Navigator - HP-Jira](https://hp-jira.external.hp.com/issues/?jql=issuetype%20%3D%20Bug%20AND%20%22Delivery%20Team%22%20in%20\(%22Device%20Mgmt%20%26%20Experience%22%2C%20%22Device%20Mgmt%202%22\)%20AND%20status%20not%20in%20\(Closed%2C%20Canceled\)%20AND%20resolution%20%3D%20Unresolved%20AND%20status%20%3D%20%22Ready%20for%20Dev%22%20ORDER%20BY%20priority%2C%20Severity)
 

