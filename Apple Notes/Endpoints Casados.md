---
apple-notes-id: D7ED3B51-A219-4E7F-A18C-4D0A8041FAAE
---
```
/inscricoes
```


```
/liderancas-auth/login
```


```
/liderancas
```


```
/turmas
```


```
/coordenador
```
### DASH

```
GET /dash/inscritos?lote=${lote}
```


```
GET /dash/lideres?lideranca=${lideranca}
```


```
GET /dash/turmas?semestre=${semestre}
```


```
GET /dash/reservas
```


```
GET /dash/pagos
```


```
GET /dash/msg-enviadas
```


```
GET /dash/loop-nao-pagos
```


```
GET /dash/turmas
```
### INSCRICOES

```
/inscricoes
```


COORDENADOR

```
/coordenador-auth/login
```


LIDER

```
/lider
```


./proxy.config.js

```
const proxy = [
  {
    "context": '/api',
    "target": 'http://localhost:3000',
    "logLevel": "debug",
    "changeOrigin": true,
    "pathRewrite": { "^/api": "" }
  }
];
module.exports = proxy;
```