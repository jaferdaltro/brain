---
apple-notes-id: 8AB238FA-F8B2-46FE-8F0C-8520831C589A
---
#grasp #design_pattern 

No padrão GRASP (General Responsibility Assignment Software Patterns), um "Controller" é um padrão de design que define uma classe que atua como intermediária entre a interface do usuário e o sistema. O objetivo do padrão "Controller" é separar a lógica da interface do usuário da lógica de negócios do sistema.
O "Controller" recebe as entradas do usuário da interface e as processa, enviando os dados relevantes para as classes de negócios (por exemplo, para as classes de modelo) para que sejam processados. Quando o processamento estiver completo, o "Controller" atualiza a interface do usuário com os resultados apropriados.
Um exemplo de aplicação do padrão "Controller" pode ser visto em um sistema de comércio eletrônico. O "Controller" receberia as entradas do usuário, como um pedido de compra, e as enviaria para as classes de negócios que processam as transações financeiras e gerenciam o estoque do produto. O "Controller" então atualizaria a interface do usuário com o status do pedido e quaisquer informações relevantes, como o tempo de entrega estimado.
O padrão "Controller" é uma técnica eficaz para manter a separação de responsabilidades entre as diferentes partes de um sistema de software e para tornar o código mais modular e fácil de manter.

                             +----------+
             +-------------->|  Model   |
             |               +----------+
+--------+   |                     ^
|        |   |                     |
|        |   |                     | Dados de entrada e saída
|        |   |                     |
| View   +---+                     |
|        |                         |
|        |                         |
|        |   |               +----------+
+--------+   |               | Controller |
             |               +----------+
             +-------------->|  (C)     |
                             +----------+

Nessa representação, a "View" representa a interface do usuário que exibe informações e recebe entradas do usuário. A "Model" representa as classes de negócios que processam as transações financeiras e gerenciam o estoque do produto.
O "Controller" age como intermediário entre a "View" e a "Model". Ele recebe as entradas do usuário da "View" e as envia para as classes relevantes na "Model" para que sejam processadas. Quando o processamento estiver completo, o "Controller" atualiza a "View" com os resultados apropriados. Isso permite que a "View" seja atualizada sem afetar a lógica de negócios da "Model".