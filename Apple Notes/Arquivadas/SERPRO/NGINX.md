---
apple-notes-id: 2FDC833D-9CF4-463C-AD85-C2A9BE11257E
---
#tecnologia 

O que é **NGINX**?
É um servidor Web leve para serviços como HTTP, proxy reverso, proxy de e-mail IMAP/POP3.


The way nginx and its modules work is determined in the configuration file. By default, the configuration file is named nginx.conf and placed in the directory /usr/local/nginx/conf, /etc/nginx, or /usr/local/etc/nginx.

No NGINX temos um móduloo conhecido como ***ngx_http_gzip_module*** que é um filtro utilizado para comprimir as respostas devolvidas pelo servidor por meio do método *gzip*. Dentro desse módulo temos a diretiza ***gzip_proxied***, que "*ativa ou desativa o gzipping de respostas para solicitações com proxy, dependendo da solicitação e da resposta*".

A diretiva *location* é quem permite rotear a solicitação para a localização correta em um sistema de arquivos. O *location* é o responsável por informar o correto local de um recurso.

O **nginx_substitutions_filter** é um módulo de substituição nativo do NGINX, sua missão é fazer "*substituições de expressões regulares e de strings fixas em corpos de resposta*".