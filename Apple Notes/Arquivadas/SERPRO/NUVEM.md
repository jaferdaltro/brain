---
apple-notes-id: 9C4474B4-73CB-4CD0-955C-7A1BEAC9A09D
---
#nuvem  #cebraspe

Julgue o item subsecutivo, com relação a cloud computing.
**As aplicações do modelo SaaS (Software as a Service) devem utilizar banco de dados separado, tal que os dados de cada empresa ficam isolados dos dados das demais empresas**.

Quando a afirmativa fala "banco de dados separado", suponho que esteja falando da localização física do servidor em que ficam armazenados os dados da empresa, mas acredito que faltou mais clareza para cravarmos que com certeza é isso. De qualquer forma, quando falamos em Computação em Nuvem, a localização física dos dados tende a ficar irrelevante, independente do tipo de oferta que está sendo feito (seja ela IaaS, PaaS ou SaaS). Assim, não é necessário que os bancos de dados estejam fisicamente separados uns dos outros. Inclusive, se várias empresas contratarem o mesmo fornecedor (várias empresas forem clientes de um mesmo serviço), é possível que a localização geográfica dos dados destas diferentes empresas seja em um mesmo datacenter.

Agora, vamos conceituar IaaS, PaaS e SaaS (trecho retirado de www.ibm.com/br-pt/cloud/learn/iaas-paas-saas):

**\[ IaaS \]** A infraestrutura como um serviço (IaaS) é uma oferta de computação em cloud na qual um fornecedor fornece aos usuários acesso aos recursos de computação, como armazenamento, redes e servidores. As empresas usam seus próprios aplicativos e plataformas dentro da infraestrutura de um provedor de serviços.
Principais recursos:
- Em vez de comprar o hardware imediatamente, os usuários pagam pela IaaS sob demanda.
- Dependendo das necessidades de processamento e armazenamento, a infraestrutura é escalável.
- Faz com que as empresas economizem os custos de adquirir e manter seu próprio hardware.
- Como os dados estão em cloud, não há nenhum ponto de falha.
- Permite a virtualização de tarefas administrativas, liberando tempo para outros trabalhos.

**\[ PaaS \]** Plataforma como um serviço (PaaS) é uma oferta de computação em cloud que fornece aos usuários um ambiente de cloud no qual podem desenvolver, gerenciar e entregar aplicativos. Além do armazenamento e de outros recursos de computação, os usuários podem usar um conjunto de ferramentas pré-montadas para desenvolver, customizar e testar seus próprios aplicativos. Principais recursos:
- O PaaS fornece uma plataforma com ferramentas para testar, desenvolver e hospedar aplicativos no mesmo ambiente.
- Permite que as organizações se concentrem no desenvolvimento, sem preocupações com a infraestrutura subjacente.
- Os provedores gerenciam a segurança, os sistemas operacionais, o software do servidor e os backups.
- Facilita o trabalho colaborativo, mesmo se as equipes trabalharem remotamente.

**\[ SaaS \]** Software como um serviço (SaaS) é uma oferta de computação em cloud que fornece aos usuários acesso a um software baseado em cloud de um fornecedor. Os usuários não instalam os aplicativos em seus dispositivos locais. Em vez disso, os aplicativos residem um uma rede de cloud remota acessada por meio da web ou de uma API. Por meio do aplicativo, os usuários podem armazenar e analisar dados e colaborar em projetos.
Principais recursos:
- Os fornecedores de SaaS fornecem aos usuários software e aplicativos por meio de um modelo de assinatura.
- Os usuários não precisam gerenciar, instalar ou fazer upgrade de software; os provedores SaaS gerenciam tudo isso.
- Os dados ficam seguros na cloud; uma falha de equipamento não resulta em perda de dados.
- O uso de recursos pode escalar dependendo das necessidades de serviço.
- Os aplicativos são acessíveis a partir de praticamente todos os dispositivos conectados à Internet, de qualquer lugar no mundo.


## Armazenamento em Bloco

O armazenamento em bloco, às vezes chamado de armazenamento em nível de bloco, é uma tecnologia usada para armazenar arquivos de dados em redes de área de armazenamento (SANs) ou em ambientes de armazenamento baseados na cloud. Os desenvolvedores preferem o armazenamento em bloco para situações de computação que exigem transporte de dados rápido, eficiente e confiável.
O armazenamento em bloco divide os dados em blocos e, em seguida, armazena esses blocos como partes separadas, cada uma com um identificador exclusivo. A SAN coloca esses blocos de dados onde eles são mais eficientes. Isso significa que ele pode armazenar esses blocos em sistemas diferentes e cada bloco pode ser configurado (ou particionado) para funcionar com sistemas operacionais diferentes.
O armazenamento em bloco também separa os dados dos ambientes do usuário, permitindo que os dados sejam distribuídos entre diversos ambientes. Isso cria vários caminhos para os dados e permite que o usuário os recupere rapidamente. Quando um usuário ou aplicativo solicita dados de um sistema de armazenamento em bloco, o sistema de armazenamento subjacente remonta os blocos de dados e apresenta os dados ao usuário ou aplicativo.




<p style="text-align:center;margin:0">
</p>