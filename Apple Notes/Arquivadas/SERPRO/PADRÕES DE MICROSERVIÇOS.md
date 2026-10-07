---
apple-notes-id: 747BAA2C-7EFD-4DB0-8B16-10BF4CEFE741
---
#arquitetura #saga #cqrs

CQRS(Command Query Responsibility Segregation)
É um padrão de design de software que **separa** e não unifica as operações de leitura(*queries*) das operações de escrita(comandos) em um sistema. A ideia central do CQRS é **dividir a lógica de uma aplicação em duas partes distintas**, uma responsável por lidar com as operações de **leitura** e outra responsável por lidar com as operações de **escrita**.
Em vez de usar um único modelo de domínio para manipular tanto as leituras quanto as escritas, o CQRS propõe a criação de dois modelos de domínio **separados**(leitura e escrita).