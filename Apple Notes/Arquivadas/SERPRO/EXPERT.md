---
apple-notes-id: 87C6DC49-B558-466E-824D-21BA9CBFDE91
---
#arquitetura #design_pattern #grasp 

No contexto do padrão GRASP (General Responsibility Assignment Software Patterns), um "Expert" é um padrão de design que indica que a responsabilidade por uma determinada tarefa deve ser atribuída a uma classe que tenha o conhecimento especializado necessário para executá-la de maneira adequada.
Em outras palavras, o padrão "Expert" sugere que uma classe deve ser responsável por uma tarefa específica se ela tiver o conhecimento e a experiência necessários para realizá-la com eficiência. Isso ajuda a manter a coesão do código e reduzir o acoplamento entre as classes.
Por exemplo, se uma aplicação tiver uma função que lide com cálculos matemáticos complexos, o padrão "Expert" pode ser aplicado, atribuindo essa responsabilidade a uma classe que tenha o conhecimento especializado em matemática, em vez de espalhar essa funcionalidade por várias classes. Dessa forma, a classe especializada pode ser facilmente modificada ou substituída sem afetar outras partes do código.

             +-------------+
             |     Sale    |
             +-------------+
                   |
                   |
                   | Venda de produtos
                   |
             +-------------+
             |   Product   |
             +-------------+
                   |
                   |
                   | Dados do produto
                   |
             +-------------+
             |  ProductDB  |
             +-------------+
                   |
                   |
                   | Acesso ao banco de dados
                   |
             +-------------+
             |    DAO      |
             +-------------+

Nesta representação, a classe "Sale" é responsável por gerenciar as vendas, enquanto a classe "Product" é responsável por gerenciar os dados do produto. A classe "ProductDB" é responsável pelo acesso ao banco de dados que armazena as informações dos produtos.
O padrão "Expert" é aplicado ao atribuir a responsabilidade pelo acesso ao banco de dados à classe "ProductDB", que tem o conhecimento especializado necessário para lidar com o armazenamento de dados em um banco de dados. A classe "DAO" (Data Access Object) atua como um intermediário entre a classe "Sale" e a classe "ProductDB", permitindo que a classe "Sale" acesse os dados do produto sem precisar ter conhecimento direto do banco de dados.
Isso ajuda a manter a coesão do código e reduzir o acoplamento entre as classes. Quando a classe "ProductDB" precisa ser atualizada ou substituída, isso pode ser feito sem afetar a lógica de negócios da classe "Sale".




#serpro #arquitetura