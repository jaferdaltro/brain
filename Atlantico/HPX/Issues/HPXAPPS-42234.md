[WINDOWS] Nickname is not reflecting in HPX device details page when updated by personalization card
https://hp-jira.external.hp.com/browse/HPXAPPS-42234

NOTE: The MFE is not receiving state update from devices-northbound hook on windows. In AA the MFE refresh the nickname as expected

**HW/SW spec:**

myHP/HPX version:49.22533.17.111.0  
UI Toolkit version: 2.0.26  
Form Factor (NB, DT, AiO, Other):  
OS version: Win11 Pro 26100

devices-northbound-api version: 1.6.4

react-personalization-mfe version: 2.5.1

**Repro steps:**

1. Install Latest ITG build.
2. Access any device details page.
3. Update device nickname using personalization card
4. check the device nickname at the top of the page --> issue
5. Refresh the page
6. The new nickname will be updated at the top of the page.

**Expected result:** 

1. Save the new nickname using personalization card  
2. Check the device nickname at the top of the page --> should show the new nickname

**Actual result:** 

1. Save the new nickname using personalization card  
2. Check the device nickname at the top of the page --> is showing the old nickname



console.log(`[TEST] Device nickname: ${nickname}`);


Apos uma investigação mais detalhada foi constatado que quando o personalization name é alterado, a atualização não acontece de imediato. 
No código foi colocado um console logo depois do deviceData.data (devicesNBApi), que só é atualizado depois do refresh da página, ou seja, a informação que deveria ser trigada no botão save do personalization não acontece.