https://refactoring.guru/pt-br/design-patterns 
## Padrões de Projeto (Design Patterns)

Padrões de projeto são soluções reutilizáveis para problemas recorrentes no design de software orientado a objetos. Eles não são código pronto, mas sim modelos/templates de como resolver um problema em diferentes contextos. O catálogo mais famoso é o do "Gang of Four" (GoF), de 1994, que os organiza em três categorias:

### 1. Padrões Criacionais

Lidam com a criação de objetos, tornando o sistema independente de como seus objetos são criados/compostos.

- **Singleton** — garante que uma classe tenha apenas uma instância, com ponto de acesso global.
- **Factory Method** — define uma interface para criar objetos, mas deixa subclasses decidirem qual classe instanciar.
- **Abstract Factory** — cria famílias de objetos relacionados sem especificar suas classes concretas.
- **Builder** — separa a construção de um objeto complexo da sua representação, permitindo criar diferentes representações passo a passo.
- **Prototype** — cria novos objetos copiando um protótipo existente.

### 2. Padrões Estruturais

Tratam da composição de classes e objetos para formar estruturas maiores.

- **Adapter** — converte a interface de uma classe em outra esperada pelo cliente.
- **Decorator** — adiciona responsabilidades a um objeto dinamicamente, sem alterar sua estrutura.
- **Facade** — fornece uma interface simplificada para um subsistema complexo.
- **Composite** — trata objetos individuais e composições de objetos de forma uniforme (estrutura de árvore).
- **Proxy** — fornece um substituto/placeholder para controlar acesso a outro objeto.
- **Bridge** — separa uma abstração de sua implementação para que ambas possam variar independentemente.

### 3. Padrões Comportamentais

Tratam da comunicação e atribuição de responsabilidades entre objetos.

- **Strategy** — encapsula algoritmos intercambiáveis, permitindo trocar o comportamento em tempo de execução.
- **Observer** — define dependência um-para-muitos, notificando automaticamente observadores quando o estado de um objeto muda.
- **Command** — encapsula uma solicitação como um objeto, permitindo parametrizar, enfileirar ou desfazer ações.
- **State** — permite que um objeto altere seu comportamento quando seu estado interno muda.
- **Template Method** — define o esqueleto de um algoritmo, deixando subclasses implementarem etapas específicas.
- **Chain of Responsibility** — passa uma solicitação por uma cadeia de handlers até que um a trate.
- **Iterator** — fornece uma forma de acessar elementos de uma coleção sequencialmente sem expor sua estrutura interna.

### Por que usar?

- Vocabulário comum entre desenvolvedores (facilita comunicação em code review, documentação).
- Soluções testadas e comprovadas, evitando "reinventar a roda".
- Facilitam manutenção e extensão do código (baixo acoplamento, alta coesão).

### Cuidado

Não force o uso de um padrão só porque existe — aplicar padrões sem necessidade real gera complexidade desnecessária ("over-engineering"). O padrão deve surgir naturalmente do problema, não o contrário.
