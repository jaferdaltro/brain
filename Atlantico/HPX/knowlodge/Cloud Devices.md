
```
await Shell.v1.graphql.query(`query Devices {
  devices {
    items {
        deviceId
        type
        identity {
          friendlyName
          serialNumber
          makeAndModel {
            name
            number
            typeId
          }
       }
    }
  }
}`)
```


### Take FF

`let experienceToggle = await System.import(`
  `'@clientos/experience-toggle-northbound-api'`
`);`

`let devices = await experienceToggle.v2.check({key: 'devices-x-discovery-cloud'})`
