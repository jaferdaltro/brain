---
apple-notes-id: DCD722EC-832F-44A3-814F-FD71FD7095DF
---
**Lista todas as imagens docker**

```
docker images -a
```

**Lista todos os containers rodando**

```
docker ps
```

**Lista todos os containers**

```
docker ps -a
```

**Inicia container**

```
docker run <nome_da_imagem>
```

**Inicia container e remove ele quando parar**

```
docker run --rm <nome_da_imagem>
```

**Inicia container usando a rede do host e remove ele quando parar**

```
docker run --rm --network host <nome_da_imagem>
```

**Inicia container existente**

```
docker start <nome_do_container> ou <id_do_container>
```

**Para container**

```
docker stop <nome_do_container> ou <id_do_container>
```

**Mata todos os container**

```
docker kill $(docker ps -q)
```

**Visualiza log do container**

```
docker logs <nome_do_container> ou <id_do_container>
```

**Visualiza log do container em tempo real**

```
docker logs -f <nome_do_container> ou <id_do_container>
```

**Deleta todos os container**
Use forçar -f para deletar docker rodando.

```
docker rm $(docker ps -a -q)
```


```
docker rm -f $(docker ps -qa)
```
**Deleta imagem**

```
docker rmi <nome_da_imagem>
```

**Deleta todas as imagens**

```
docker rmi $(docker images -q)
```

**Deleta todas as imagens sem pendências**

```
docker rmi $(docker images -q -f dangling=true)
```

**Deleta volumes sem pendências**

```
docker volume rm -f $(docker volume ls -f dangling=true -q)
```

**Entra no container via ssh local**

```
sudo docker exec -it <nome_do_container> bash
```

**Docker attach/detach**

```
docker attach <container>
docker detach <container>
```

To detach from the container without stopping it, you can press the Ctrl + P and Ctrl + Q keys together. This will detach your terminal from the container's process and return you to the host machine's command prompt.

### Builda um contêiner que tem Dockerfile 

```
docker-compose up -d —no-deps —build <app>

```
### Usa terminal do Container

```
docker compose run —rm <app> bash
```