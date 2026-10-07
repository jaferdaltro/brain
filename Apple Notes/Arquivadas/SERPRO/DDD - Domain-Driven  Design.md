---
apple-notes-id: 25AB5833-43EF-4F82-8641-F00E6B88C6DF
---
#arquitetura #ddd

DDD nos conduz através dos seus blocos de construção a utilizar alguns princípios de arquitetura e design patterns consagrados, entre eles:
1. Isolamento do domínio com arquitetura em camadas.
2. Representação do modelo através de artefatos de software bem definidos (entities, value objects, services, factories, repositories, specs, modules, etc).
3. Gerenciamento do ciclo de vida de objetos do domínio com aggregates.

Dessa forma, o DDD permite a representação do modelo por meio de artefatos de software bem definidos.



O **DDD** traz como benefício o isolamento das regras de negócios da lógica de apresentação, que é a interface com o usuário.



No DDD a modelagem e a implementação atuam de forma conjunta.



*Domain-Driven Design* ou Projeto Orientado a Domínio é um padrão de modelagem de software orientado a objetos que procura reforçar conceitos e boas práticas relacionadas à OO. Essencialmente as relacionadas abaixo:
- Alinhamento do código com o negócio;
- Favorecer reutilização;
- Mínimo de acoplamento;
- Independência da Tecnologia.
Além dos conceitos de OO, DDD baseia-se em duas premissas principais:
- O foco principal deve ser o **domínio**;
- Domínios complexos devem estar baseados em um **modelo**.
Dessa maneira, projetar um software orientado ao domínio é uma tarefa muito mais difícil do que simplesmente “ir fazendo”, uma vez que trazer o conhecimento da cabeça de um especialista de negócio para um software, de forma organizada, é algo complexo. Não envolve um planejamento baseado em especulações para um futuro que pode mudar.
 
Finalizando, seu foco é na modelagem das entidades principais de negócio usando a linguagem adequada daquele domínio para facilitar a manutenção, extensão e entendimento. Volta-se para uma arquitetura de negócio sólida, que considera os aspectos subjacentes do contexto complexo do domínio que o sistema está inserido. Assim, no futuro, é possível realizar modificações através da reutilização de códigos, mudanças em módulos específicos e facilidade em alterar as regras de negócios, caso o DDD tenha sido implementado corretamente no passado.



*O DDD é uma abordagem para o desenvolvimento de software para necessidades complexas, conectando profundamente a implementação a um modelo em evolução dos principais conceitos de negócios.*



O padrão ***Naked Objects*** é uma abordagem orientada a objetos onde os objetos de domínio ficam expostos na interface de usuário, e o usuário tem o poder manipulá-los diretamente através da realização de invocações dos métodos implementados por esses objetos  Nessa abordagem, o projeto de codificação de todas as classes deve respeitar um dos mais importantes princípios da Orientação a Objetos, que é a completude comportamental dos objetos, ou seja, os objetos devem implementar por completo o que eles representam. A aplicação desse padrão retira do programador a necessidade de implementar interface de usuário ou mecanismos de segurança e persistência, tendo responsabilidade apenas sobre a criação dos objetos de domínio da aplicação, os quais devem implementar de forma completa todo o comportamento que eles propõem representar. Assim, como a ideia inicial do DDD é voltar à uma modelagem OO mais pura, esquecendo de como os dados são persistidos e se preocupando em como representar melhor as necessidades de negócio em classes e comportamentos (métodos), o padrão *naked objects* é o indicado para ajudar a prototipar, desenvolver e implantar rapidamente aplicativos orientados a domínio no âmbito DDD (*domain driven design*).

<p style="text-align:center;margin:0">
</p>