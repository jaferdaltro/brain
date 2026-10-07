---
apple-notes-id: 92B3462D-2AF2-468C-B787-1F6E18387C16
---
**Instalação**

```
npm i -D prisma
```

**Rodar o prisma**

```
npx prisma init
```

### Configuração PRISMA

```
DATABASE_URL=“mysql://root:root@localhost:3306/api”
```

Depois de criado a tabela no banco de dados: rodar

```
npx prisma db pull
```


```
@@map("users")
```


```
npx prisma generate
```