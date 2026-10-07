---
apple-notes-id: 5A6B1DAA-6FB7-48DE-AE06-B27C4822CE2F
---
#seguranca

**Confidencialidade**: Informação só será acessada por pessoas autorizadas.

**Ataques passivos**: são aqueles que não alteram a informação, nem o seu fluxo normal, no canal sob escuta. 

**Ataques ativos**: são os que intervêm no fluxo norma de informação, quer alterando o seu conteúdo, quer produzindo informação não fidedigna.

--
**QUESTÃO:**
As decisões acerca da <u>retenção do risco</u> são tomadas com base na inclusão, na exclusão ou na alteração de controles, para se reduzir o risco, conforme a norma aplicável.
**Gabarito: ERRADO.**
 
A questão trata das opções de tratamento do risco (uma das etapas do gerenciamento de risco). Na retenção, como o próprio nome sugere, a decisão é assumir o risco, baseando-se em uma análise de custo benefício. **Portanto, não se trata da inclusão, exclusão ou alteração dos controles. Quem faz isso quer na verdade modificar o risco!**
 
Veja uma descrição disso na ISO 27005/2011, referência em gerenciamento de riscos de TI:

***9.2 Modificação do risco***
*Ação: Convém que o nível de risco seja gerenciado através da inclusão, exclusão ou alteração de controles, para que o risco residual possa ser reavaliado e então considerado aceitável.*
 
<b><i><u>9.3 Retenção do risco</u></i></b>
*Ação: Convém que as decisões sobre a retenção do risco, sem outras ações adicionais, sejam tomadas tendo como base a avaliação de riscos. N*O*TA* O *tópico ABNT NBR ISO/IEC 27001:2006 4.2.1 f 2) "aceitação do risco, consciente e objetiva, desde que claramente satisfazendo as políticas da organização e os critérios para aceitação do risco” descreve a mesma atividade.*

***9.4 Ação de evitar o risco***
*Ação: Convém que a atividade ou condição que dá origem a um determinado risco seja evitada.*
 
***9.5 Compartilhamento do risco***
*Ação: Convém que um determinado risco seja compartilhado com outra entidade que possa gerenciá-lo de forma mais eficaz, dependendo da avaliação de riscos.*
 
*Diretrizes para implementação:*
 
*Se o nível de risco atende aos critérios para a aceitação do risco,* ***não há necessidade de se implementar controles adicionais e pode haver a retenção do risco.***
--

A análise de riscos é fundamental em qualquer instituição, já que precisamos otimizar o risco para desempenhar com melhor segurança as atividades. Nesse sentido, a Norma ISO 27005 surgiu para orientar as organizações sobre Boas Práticas na Gestão de Riscos. 
 
Na análise de riscos, devemos levar em consideração tanto riscos quantitativos como qualitativos, já que a combinação dos dois parâmetros fornece melhor subsídio para as decisões. Vejamos o que diz a Norma sobre o assunto:
 
***A análise de riscos designa valores para a probabilidade e para as consequências de um risco. Esses valores podem ser de natureza quantitativa ou qualitativa****. A análise de riscos é* <i><u>baseada nas consequências e na probabilidade estimadas</u></i>*. Além disso, ela pode considerar o custo-benefício, as preocupações das partes interessadas e outras variáveis, conforme apropriado para a avaliação de riscos. O* ***risco estimado*** *é uma combinação da probabilidade de um cenário de incidente e suas consequências.*


De acordo com a NBR ISO/IEC 27005 (p. 25), na **avaliação das consequências da análise de riscos**, o valor do impacto de um ativo de informação afetado por uma violação de segurança é determinado de duas maneiras:
 
- o valor da reposição do ativo, composto pelo custo da recuperação e da reposição da informação;
 
- as consequências ao negócio relacionadas à perda ou ao comprometimento do ativo, como as possíveis consequências adversas de caráter empresarial, legal ou regulatórias causadas pela divulgação indevida, modificação, indisponibilidade e/ou destruição de informações ou de outros ativos de informação.


O*s critérios para a aceitação do risco podem ser mais complexos do que somente a determinação se o risco residual está, ou não, abaixo ou acima de um limite bem definido. Em alguns casos, o nível de risco residual pode não satisfazer os critérios de aceitação do risco, pois os critérios aplicados não estão levando em conta as circunstâncias predominantes no momento. Por exemplo, pode ser válido argumentar que é preciso que se aceite o risco, pois os benefícios que o acompanham são muito atraentes ou porque os custos de sua modificação são demasiadamente elevados. Tais circunstâncias indicam que os critérios para a aceitação do risco são inadequados e convém que sejam revistos, se possível. No entanto, nem sempre é possível rever os critérios para a aceitação do risco no tempo apropriado.* ***Nesses casos, os tomadores de decisão podem ter que aceitar riscos*** *que não satisfaçam os critérios normais para o aceite. Se isso for necessário,* ***convém que o tomador de decisão comente explicitamente sobre os riscos e inclua uma justificativa para a sua decisão de passar por cima dos critérios normais para a aceitação do risco.***

***Avaliação de riscos de segurança da informação***
*A organização deve definir e aplicar um processo de avaliação de riscos de segurança da informação que:*
*a) estabeleça e mantenha critérios de riscos de segurança da informação que incluam: 1) os critérios de aceitação do risco; e 2) os critérios para o desempenho das avaliações dos riscos de segurança da informação; b)* ***assegure que as contínuas avaliações de riscos de segurança da informação produzam resultados comparáveis, válidos e consistentes;***
--

***Tipos de ataques de XSS***
*Cross-site scripting pode ser classificado em três categorias principais — XSS Armazenado, XSS Refletido e XSS baseado em DOM.*
 
***Cross-site scripting armazenado (XSS Persistente)***
*XSS Armazenado, também conhecido como XSS Persistente, é considerado o tipo de ataque XSS mais prejudicial.* O *XSS Armazenado* ***ocorre quando a entrada fornecida pelo usuário é armazenada e, em seguida, processada em uma página da Web. Os pontos de entrada típicos para XSS Armazenado incluem fóruns de mensagens, comentários em blogs, perfis de usuário e campos de nome de usuário.*** *Um invasor normalmente explora essa vulnerabilidade injetando cargas de XSS em páginas populares de um site ou passando um link para uma vítima, induzindo-a a visualizar a página que contém a carga de XSS armazenada. A vítima visita a página e a carga útil é executada no lado do cliente pelo navegador da vítima.*
 
***Cross-site scripting Refletido (XSS Não persistente)***
*O tipo mais comum de XSS é conhecido como XSS Refletido (também conhecido como XSS Não persistente). Nesse caso, a carga útil do invasor deve fazer parte da solicitação enviada ao servidor da Web. Em seguida, é refletido de volta de maneira que a resposta HTTP inclua a carga útil da solicitação HTTP.* ***Os invasores usam links maliciosos, e-****mails de phishing e outras técnicas de engenharia social para induzir a vítima a fazer uma solicitação ao servidor. A carga útil XSS refletida é então executada no navegador do usuário.*
 
O *XSS Refletido não é um ataque persistente, portanto, o invasor precisa entregar a carga útil a cada vítima. Esses ataques costumam ser feitos por meio de redes sociais.*
 
***Cross-site scripting baseado em DOM***
*XSS baseado em DOM refere-se a uma vulnerabilidade de cross-site scripting que aparece no DOM (Document Object Model) em vez de parte do HTML. Em ataques de cross-site scripting refletidos e armazenados, você pode ver a carga útil da vulnerabilidade na página de resposta, mas no cross-site scripting baseado em D*O*M, o código-fonte HTML do ataque e a resposta serão os mesmos, ou seja, a carga útil não pode ser encontrada na resposta. Ele só pode ser observado em tempo de execução ou investigando o DOM da página.*
 
*Um ataque XSS baseado em D*O*M é geralmente um ataque do lado do cliente, e a carga maliciosa nunca é enviada ao servidor. Isso torna ainda mais difícil a detecção de WAFs (Web Application Firewalls) e engenheiros de segurança que analisam os logs do servidor porque nunca veem o ataque.* O*s objetos DOM que são manipulados com mais frequência incluem o URL (document.URL), a parte âncora do URL (location.hash) e o Referrer (document.referrer).*


--

O *controle de acesso reforça a política de forma que os usuários não possam agir fora de suas permissões pretendidas. As falhas geralmente levam à divulgação não autorizada de informações, modificação ou destruição de todos os dados ou à execução de uma função comercial fora dos limites do usuário. Vulnerabilidades comuns de controle de acesso incluem:*
*Violação do princípio de privilégio mínimo ou negação por padrão, em que o acesso deve ser concedido apenas para recursos, funções ou usuários específicos, mas está disponível para qualquer pessoa.*
*Ignorar as verificações de controle de acesso modificando a URL (violação de parâmetros ou navegação forçada), o estado interno do aplicativo ou a página HTML ou usando uma ferramenta de ataque que modifica solicitações de API.*
*Permitir visualizar ou editar a conta de outra pessoa, fornecendo seu identificador exclusivo (referências diretas inseguras de objetos)*
*Acessando a API com controles de acesso ausentes para POST, PUT e DELETE.*
*Elevação de privilégio. Atuar como usuário sem estar conectado ou atuar como administrador quando conectado como usuário.*
*Manipulação de metadados, como reprodução ou adulteração de um token de controle de acesso JS*O*N Web Token (JWT), ou um cookie ou campo oculto manipulado para elevar privilégios ou abusar da invalidação de JWT.*
*A configuração incorreta do C*O*RS permite acesso à API de origens não autorizadas/não confiáveis.*
*Força a navegação para páginas autenticadas como usuário não autenticado ou para páginas privilegiadas como usuário padrão.*
***Como prevenir***
*O controle de acesso só é eficaz em código confiável do lado do servidor ou API sem servidor, em que o invasor não pode modificar a verificação ou os metadados do controle de acesso.*
*Exceto para recursos públicos, nega por padrão.*
*Implemente mecanismos de controle de acesso uma vez e reutilize-os em todo o aplicativo, incluindo a minimização do uso de compartilhamento de recursos entre origens (CORS).*
*Os controles de acesso do modelo devem impor a propriedade do registro em vez de aceitar que o usuário possa criar, ler, atualizar ou excluir qualquer registro.*
*Os requisitos exclusivos de limite de negócios do aplicativo devem ser impostos pelos modelos de domínio.*
 
***Desabilite a lista de diretórios do servidor web e certifique-se de que os metadados do arquivo (por exemplo, .git) e os arquivos de backup não estejam presentes nas raízes da web.***
 
*Registre falhas de controle de acesso, alerte os administradores quando apropriado (por exemplo, falhas repetidas).*
*API de limite de taxa e acesso ao controlador para minimizar os danos causados ​​por ferramentas de ataque automatizadas.*
 
O*s identificadores de sessão com estado devem ser invalidados no servidor após o logout.* O*s tokens JWT sem estado devem ter vida curta para que a janela de oportunidade para um invasor seja minimizada. Para JWTs de longa duração, é altamente recomendável seguir os padrões* O*Auth para revogar o acesso.*

### Indentificação das consequências 
Uma lista de ativos, uma listta de processos do negócio e uma lista de ameaças e vulnerabilidades, quando aplicável, relacionadas aos ativos e sua relevância.
--
**Analisar e avaliar** riscos então alinhados com a fase de planejar do SGSI.
**A implementação do plano de tratamento de riscos é a**  ***primeira etapa da fase da etapa Fazer (Do).*** 


| Processo do SGSI | Processo de gestão de fiscos de segurança da informação |
| -- | -- |
| Planejar | Definição do contexto<br>Processo de avaliação de riscos<br>Definição do plano de tratamento de risco<br>Aceitação do risco |
| Executar | Implementação do plano de tratamento de risco |
| Verificar | Monitoramento contínuo e análise crítica de riscos |
| Agir | Manter e melhorar o processo de Gestão de Riscos de Seguraça da Informação. |