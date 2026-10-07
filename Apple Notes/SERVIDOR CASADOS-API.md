---
apple-notes-id: 05882CDE-58C4-4577-B1F8-F9F00863FDA0
---
#igreja #app #casados 

## Maquinas
1. *d8d9936c2936e8*
2. *784ee92be1d4e8*
3. *48edd49b3e0948* **(DB)**


## Banco

### Proxy

```
flyctl proxy 15432:5432 -a casados-api-db
```

### Resetar o banco

```
fly ssh console -C "/rails/bin/rails db:drop:_unsafe DISABLE_DATABASE_ENVIRONMENT_CHECK=1"
```

### Console

```
fly ssh console -a casados-api-db
```
run env then you’ll see all envs including username and password.


```
postgresql://casados-api-db.flycast
```



```
fly postgres users list --app casados-api-db
```

### Acessar o cluster

```
psql "sslmode=require host=casados-api-db.fly.dev dbname=postgresql://casados-api-db.flycast user=casados_api"
```

### DB STRING

```
postgres://casados_api:HFLuruUtLhu5GFk@casados-api-db.flycast:5432/casados_api?sslmode=disable
```
Username: casados_api
Password: HFLuruUtLhu5GFk
Hostname: casados-api-db.internal



```
jdbc:mysql://154.49.246.206:3306/casados
```
## App

### Interactive shell

```
fly ssh console --pty -C '/bin/bash'
```


### Rails console

```
fly ssh console --pty -C "/rails/bin/rails console"
```


### Pra ver o status por máquina

```
fly machine status 48edd49b3e0948 --app casados-api-db
```

### Meu IP do Banco

```
66.241.124.175
```

### Pra conseguir um ipv4

```
fly ips allocate-v4 --app casados-api-db --shared
```


### RAILS MASTER KEY


```
fly ssh console -C 'printenv RAILS_MASTER_KEY'
```

secret_key_base: 9be5334843289633d49697c3ce704d4e1587f3954487b71ca014c95e7a13e018e5b76e0ee674c3174a2abebf7135c46e025e4cf03f06dcdf1159571439    14a79f

### PG DUMP

```
pg_dump postgres://casados_api:HFLuruUtLhu5GFk@localhost:15432/casados-api-db --verbose --other --flags --here > ./db_dump
```

### REDIS


```
REDIS_URL=redis://default:casados_api:HFLuruUtLhu5GFk@casados-api-redis-host.internal:6379
```