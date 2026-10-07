---
apple-notes-id: 5AA784E4-3EB6-4159-88BB-516F4C0FF5BB
---
#seguranca #oauth

Parte com capacidade para conceder acesso(token) aos recursos é o **servidor de autorização.** O servidor de recursos oferece o recurso protegido mediante a apresentação do acesso(token)


***OAuth 2 foi construído em cima de 4 papéis, sendo:***
- ***Resource Owner -*** ***pessoa ou entidade que concede o acesso aos seus dados****. Também chamado de dono do recurso.*
- ***Client -*** *é a aplicação que interage com o Resource Owner, como por exemplo o browser, falando no caso de uma aplicação web.*
- ***Resource Server - a API que está exposta na internet e precisa de proteção dos dados****. Para conseguir acesso ao seu conteúdo é necessário um token que é emitido pelo authorization server.*
- ***Authorization Server -*** ***responsável por autenticar o usuário*** *e emitir os tokens de acesso. É ele que possui as informações do resource owner (o usuário), autentica e interage com o usuário após a identificação do client.*

<p style="text-align:center;margin:0"><b><i>Como funciona?</i></b>
</p>



![[FLUXO-IMG.png]]



*Na imagem acima, podemos ver como geralmente funciona o fluxo de autorização.*
1. ***Solicitação de autorização*** *Nessa primeira etapa o cliente (aplicação) solicita a autorização para acessar os recursos do servidor do usuário*
2. ***Concessão de autorização*** *Se o usuário autorizar a solicitação, a aplicação recebe uma concessão de autorização.*
3. ***Concessão de autorização*** *O cliente solicita um token de acesso ao servidor de autorização (API) através da autenticação da própria identidade e da concessão de autorização.*
4. ***Token de acesso*** *Se a identidade da aplicação está autenticada e* ***a concessão de autorização for válida, o servidor de autorização (API) emite um token de acesso para a aplicação.*** *O cliente já vai ter um token de acesso para gerenciar e a autorização nessa etapa já está completa.*
5. ***Token de acesso*** *Quando o cliente precisar solicitar um recurso ao servidor de recursos, basta* ***apresentar o token de acesso.***
6. ***Recurso protegido*** *O servidor de recursos fornece o recurso para o cliente, caso o token de acesso dele for válido.*