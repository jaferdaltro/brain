
[https://pages.github.azc.ext.hp.com/HPX/docs/windows/guides/property-override/#feature-switch-override](https://pages.github.azc.ext.hp.com/HPX/docs/windows/guides/property-override/#feature-switch-override)

![[Pasted image 20260513095540.png]]

`C:\Users\\AppData\Local\Packages\AD2F1837.myHP_v10z8vjag6ke6\LocalState`

`cd $PWD/AppData/Local/Packages/AD2F1837.myHP_v10z8vjag6ke6/LocalState`

`properties.json`
```
{
  "@hp-af/feature-switch/overrides": {
    "devices-x-firstdevicecard": false,
    "devices-x-devicelist": true,
    "monitor-x-devicelist": false,
    "printer-x-devicedetails": false,
    "support-x-warrantydetail": false
  }
}
```


#### DEVICE FF LIST

```
  [DeviceType.PRINTER]: 'printer-x-devicedetails',

  [DeviceType.PC]: 'pc-x-devicedetails',

  [DeviceType.PEN]: 'pen-x-detailspage',

  [DeviceType.KEYBOARD]: 'keyboard-x-detailspage',

  [DeviceType.DOCK]: 'dock-x-detailspage',

  [DeviceType.MOUSE]: 'mouse-x-detailspage',

  [DeviceType.AUDIO]: 'audio-x-devicedetails',

  [DeviceType.MONITOR]: 'monitor-x-devicelist'
```

`Criar Jira com a requisição de Feature Flag`

`Ex: [https://hp-jira.external.hp.com/browse/HPXAPPS-28962](https://hp-jira.external.hp.com/browse/HPXAPPS-28962)`

`HPXFeatureManifest`

`[https://hp.sharepoint.com/:x:/r/teams/HPX/_layouts/15/doc2.aspx?sourcedoc=%7BF24AFAC4-B85F-4BD5-9338-2273312DA43F%7D&file=HPXFeatureManaifest.xlsx&action=default&mobileredirect=true&wdOrigin=TEAMS-MAGLEV.p2p_ns.rwc&wdExp=TEAMS-TREATMENT&wdhostclicktime=1749496539549&web=1](https://hp.sharepoint.com/:x:/r/teams/HPX/_layouts/15/doc2.aspx?sourcedoc=%7BF24AFAC4-B85F-4BD5-9338-2273312DA43F%7D&file=HPXFeatureManaifest.xlsx&action=default&mobileredirect=true&wdOrigin=TEAMS-MAGLEV.p2p_ns.rwc&wdExp=TEAMS-TREATMENT&wdhostclicktime=1749496539549&web=1)`



