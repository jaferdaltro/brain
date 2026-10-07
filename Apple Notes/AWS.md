---
apple-notes-id: 5225F969-72BC-4A03-84B5-B2E546180341
---
Abertura de conta
### [jafer.daltro@icloud.com](mailto:jafer.daltro@icloud.com)

# Nível Gratuito da AWS
[**https://aws.amazon.com/pt/free/?trk=ca1f5106-3c80-477a-93fd-1a3cea264b5c&sc_channel=ps&ef_id=CjwKCAjwgeLHBhBuEiwAL5gNEQtVyhXsTsnlQFcnEh74GR9Ctd9mWhqM61QWTjpUZewqp7A3VlhVTRoCHnwQAvD_BwE:G:s&s_kwcid=AL!4422!3!561843094929!e!!g!!aws!15278604629!130587771740&gad_campaignid=15278604629&gbraid=0AAAAADjHtp8NSGZ_YYpSvWzFczWjKof78**](https://aws.amazon.com/pt/free/?trk=ca1f5106-3c80-477a-93fd-1a3cea264b5c&sc_channel=ps&ef_id=CjwKCAjwgeLHBhBuEiwAL5gNEQtVyhXsTsnlQFcnEh74GR9Ctd9mWhqM61QWTjpUZewqp7A3VlhVTRoCHnwQAvD_BwE:G:s&s_kwcid=AL!4422!3!561843094929!e!!g!!aws!15278604629!130587771740&gad_campaignid=15278604629&gbraid=0AAAAADjHtp8NSGZ_YYpSvWzFczWjKof78) 

# AWS LightSail
#alura #devops 

Dominio Barato - https://www.namecheap.com/


![[Pasted Graphic 1 20.png]]

*Se for colocar em definitivo colocar o TTL em 60 min*

Se for colocar em produção é importante que tenha um ip estático vinculado a máquina
	Se não vincular o ip estático a uma instância será feita uma cobrança adicional.


### Acessar máquina criada


```
ssh -i lightsail-rmerces.pem ubuntu@44.205.17.187
```

Local onde encontro o html default no ubuntu

```
/var/www/html/
```


### Anexar Disco Extra a instância

Para anexar o disco à instância, seguiremos quatro etapas:
1. Fazer com que o Linux reconheça o disco fisicamente
2. Particionar o disco
3. Formatar o disco, instalando o *file system*
4. Montar o disco

Para verificar os dispositivos reconhecidos


```
sudo sfdisk -l
```
 
Informações sobre as partições (saber quais discos estão montados)


```
df -h
```

Criar partições 


```
sudo fdisk 
```

Formatacão


```
sudo mkfs.ext4 
```
 
Montagem na Inicialização


```
/etc/fstab
```
Checar a montagem sem reiniciar


```
sudo mount -a
```

[Artigo de como funciona o /etc/fstab](https://wiki.debian.org/pt_BR/fstab#:~:text=O%20arquivo%20fstab%20%28%2Fetc%2Ffstab%29%20%28ou%20tabela%20de%20sistemasintegrados%20ao%20sistema%20de%20arquivos%20de%20sistema%20geral.)