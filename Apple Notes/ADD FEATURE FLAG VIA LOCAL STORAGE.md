---
apple-notes-id: 4ED9BBD3-5AE9-43BF-BB5F-9C051836F62D
---
#feature_flag #local_storage 

## Adicionando uma chave no manifest

```
const man = localStorage.getItem('clientosManifestOverride')
const data = JSON.parse(man)
data.northboundAPIs.experienceToggle.keyMap["devices- x-discovery-cloud"] = {
          "defaultValue": true
        };
localStorage.setItem('clientosManifestOverride', data);
```



```
devices-x-progressiveloading
```