---
apple-notes-id: A33C8D54-863C-4D55-A59D-30D24B0F2DE8
---
#engenharia 


*O* <b><i><u>Quality Function Deployment</u></i></b> *(QFD) é uma técnica de gerenciamento de qualidade que* <b><i><u>traduz as necessidades do cliente em requisitos técnicos para o software</u></i></b>*. Originalmente desenvolvido no Japão e usado pela primeira vez no Estaleiro Kobe da Mitsubishi Heavy Industries, Ltd., no início da década de 1970, o QFD “concentra-se em maximizar a satisfação do cliente a partir do processo de engenharia de software \[ZUL92\].” Para isso, o QFD enfatiza uma compreensão do que é valioso para o cliente e, em seguida, implanta esses valores durante todo o processo de engenharia. O QFD identifica três tipos de requisitos \[ZUL92\]:
Requisitos normais. Os objetivos e metas que são declarados para um produto ou sistema durante as reuniões com o cliente. Se esses requisitos forem presente, o cliente fica satisfeito. Exemplos de requisitos normais podem ser tipos solicitados de exibições gráficas, funções específicas do sistema e níveis de desempenho.
Requisitos esperados. Esses requisitos estão implícitos ao produto ou sistema e pode ser tão fundamental que o cliente não declará-los. Sua ausência será motivo de grande insatisfação. Exemplos de requisitos esperados são: facilidade de interação homem/máquina, correção e confiabilidade operacional geral e facilidade de instalação de software.*
*Exigências emocionantes. Esses recursos vão além das expectativas do cliente e se mostram muito satisfatórios quando presentes. Por exemplo, software de processamento de texto é solicitado com recursos padrão. O produto entregue contém vários recursos de layout de página que são bastante agradáveis e
inesperado.*

### Engenharia de Sistemas 
Se preocupa com todos os aspectos do desenvolvimento de sistemas computacionais, incluindo engenharia de hardware, software e processo.

### Engenharia de Software
 é uma disciplina da engenharia que se preocupa com todos aspectos da produção de software, desde os estágios iniciais da especificação do sistema até sua manutenção, quando o sistema já está sendo usado. 

### 4 ETAPAS FUNDAMENTAIS DE PROCESSOS DE SOFTWARE
1. **Especificação de software**. A funcionalidade do software e as restrições a seu funcionamento devem ser definidas.
	

2. **Projeto e Implementação de software.** O software deve ser produzido para atender às especificações
3. **Validação de software**. O software deve ser validade para garantir que atenda às demandas do cliente.
4. **Evolução de software**. O software deve evoluir para atender às necessidades de mudanças dos clientes.




--

***Riscos de projeto****. Riscos que afetam o cronograma ou os recursos de projeto. Um exemplo de um risco de projeto é a perda de um projetista experiente. Encontrar um projetista substituto com competência e experiência adequados pode demorar muito tempo e, por conseguinte, o projeto de software vai demorar mais tempo para ser concluído.*

***Riscos de produto.*** *Riscos que afetam a qualidade ou o desempenho do software que está sendo desenvolvido. Um exemplo de um risco de produto é a falha de um componente comprado para o desempenho esperado, podendo afetar o desempenho geral do sistema de forma mais lenta do que o esperado.*

***Riscos de negócio.*** *Os riscos que afetam a organização que desenvolve ou adquire o software. Por exemplo, um concorrente que introduz um novo produto é um risco empresarial. A introdução de um produto competitivo pode significar que as suposições feitas sobre vendas de produtos de software existentes podem ser excessivamente otimistas.*


*Um* ***protótipo*** *é uma versão inicial de um sistema de software, usado para demonstrar conceitos, experimentar opções de projeto e descobrir mais sobre o problema e suas possíveis soluções. O desenvolvimento rápido e iterativo do protótipo é essencial para que os custos sejam controlados e os stakeholders do sistema possam experimentá-lo no início do processo de software.*
--

**Dentre as técnicas existentes de elicitação de requisitos baseadas em cenários, os casos de uso são modelos que ajudam a identificar agentes e interações do sistema.**

 **Elicitação** significa **levantamento** de requisitos, e no caso da elicitação baseada em cenários, há uma reflexão acerca das interações de uso do sistema (como por exemplo, os modos em que um usuário pode interagir com o sistema), situação em que os casos de uso podem ser muito úteis.

De acordo com Sommerville, em seu livro "Engenharia de Software - 3a edição":
*A* <b><i><u>elicitação baseada em cenários</u></i></b> *envolve o trabalho com os stakeholders para* <b><i><u>identificar cenários e capturar detalhes</u></i></b> *que serão incluídos nesses cenários. Os cenários podem ser escritos como texto, suplementados por diagramas, telas etc. Outra possibilidade é uma abordagem mais estruturada, em que cenários de eventos ou* <b><i><u>casos de uso podem ser usados</u></i></b>*.*
Ainda de acordo com Sommerville:
*Os* <b><i><u>casos de uso</u></i></b> *são uma* <b><i><u>técnica de descoberta de requisitos</u></i></b> *introduzida inicialmente no método Objectory (JACOBSON et al., 1993). Eles já se tornaram uma característica fundamental da linguagem de modelagem unificada (UML — do inglês unified modeling language). Em sua forma mais simples,* <b><i><u>um caso de uso identifica os atores envolvidos em uma interação e dá nome ao tipo de interação. Essa é, então, suplementada por informações adicionais que descrevem a interação com o sistema</u></i></b>*. A informação adicional pode ser uma descrição textual ou um ou mais modelos gráficos, como diagrama de sequência ou de estados da UML. Os casos de uso são documentados por um diagrama de casos de uso de alto nível. O conjunto de casos de uso representa todas as possíveis interações que serão descritas nos requisitos de sistema. Atores, que podem ser pessoas ou outros sistemas, são representados como figuras ‘palito’. Cada classe de interação é representada por uma elipse. Linhas fazem a ligação entre os atores e a interação. Opcionalmente, pontas de flechas podem ser adicionadas às linhas para mostrar como a interação se inicia. Essa situação é ilustrada na Figura 4.6, que mostra alguns dos casos de uso para o sistema de informações de pacientes. Não há distinção entre cenários e casos de uso que seja simples e rápida. Algumas pessoas consideram cada caso de uso um cenário único; outros, como sugerido por Stevens e Pooley (2006), encapsulam um conjunto de cenários em um único caso de uso. Cada cenário é um segmento através do caso de uso. Portanto, seria um cenário para a interação normal além de cenários para cada possível exceção. Você pode, na prática, usá-los de qualquer forma.*

*--*

Arquitetura de software é por vezes definida como o processo utlizado para conversão das características de um software em algo sólido para atender as expectativas do negócio.
 
As características, citadas acima, são utilizadas para descrever os requisitos de software em nível operacional e técnico. Na arquitetura ainda temos alguns padrões, dentre os quais existem os microservissos, servless, orientado a eventos, dentre outros.
 
O Design de sofware, por sua vez, é quem se preocupa em codificar toda a arquitetura. Aqui são utilizados, portanto, os padrões de design, por exemplo, o Factory.
 
Assim, a diferença entre arquitetura e desing de software é que a
 
*arquitetura do software é responsável pelo esqueleto e pela infraestrutura de alto nível de um software, o design do software é responsável pelo design do nível de código, como o que cada módulo está fazendo, o escopo das classes e os objetivos das funções*

--
### Processos de apoio
- Medição 
- Garantia da qualidade
- Verificação
- Validação

**Os processos de gerência** se preocupam com o planejamento e também o acompanhamento do projeto. Dentre seus processos estão a realização de estimativas, elaboração de cronogramas, análise de riscos, dentre outros.
--

Os **7 princípios da arquitetura de informação**, presentes no livro Information Architecture for the World Wide Web, de Peter Morville e Louis Rosenfeld, são:
 
- **Organizar** (estabelecer opções de construção do ambiente digital);
- **Navegar** (aprender com o usuário, seja através de informações fornecidas por ele ou pelo entendimento de seu comportamento nos ambientes digitais);
- **Nomear** (identificação de áreas, seja através de palavras ou ícones - ou ambos);
- **Buscar** (forma de indexar informações para busca eficaz);
- **Pesquisar** (caminho para construção do conteúdo);
- **Desenhar** (elaboração de testes para validação da arquitetura da informação, antes mesmo da construção do protótipo ou interface); 
- **Mapear** (estruturar visualmente a arquitetura da informação. Ex.: fluxograma).
 
O **planejamento de navegação e a redução da informação** são atividades relacionadas ao design de uma página web ou interface de um sistema. O planejamento de navegação busca mostrar as telas que serão mostradas a partir de ações especificas do usuário de um sistema ou sítio web. Já a redução da informação tem como objetivo possibilitar que o sistema ou site tenham as informações essenciais a sua utilização evitando assim que o excesso de informação dificulte ao usuário encontrar o que procura.

outra resposta:
A **arquitetura da informação é composta pelos seguintes sistemas**:
 
- **Sistema de navegação:** define a maneira de se movimentar pelas informações e determina qual caminho será necessário aos usuários percorrerem para chegar a uma determinada informação.
- **Sistema de organização:** define como deve ser agrupado e categorizado o conteúdo.
- **Sistema de busca:** define as perguntas que poderão ser feitas pelo usuário e as respectivas respostas que serão recebidas.
- **Sistema de rotulação:** define-se os nomes para cada categoria de informação (rótulos, ou títulos de menu, de página, ícones ou imagens para áreas do site). Deve sempre se pensar no usuário. São também definidas a maneira de representação e apresentação da informação, com a associação de símbolos para cada elemento de informação.

--
De acordo com Sommerville,  **um sistema de software** desenvolvido profissionalmente é, com frequência, mais do que apenas um programa; ele normalmente **consiste em uma série de programas separados e arquivos de configuração** que são usados para configurar esses programas. Isso pode incluir **documentação do sistema**, que descreve a sua estrutura**; documentação do usuário**, que explica como usar o sistema; e **sites**, para usuários baixarem a informação recente do produto.

**Engenharia de software** é uma disciplina de engenharia cujo foco está em **todos os aspectos da produção de software**, desde os estágios iniciais da especificação do sistema até sua manutenção, quando o sistema já está sendo usado. Os **princípios** da Engenharia de Software **constituem a base dos métodos, tecnologias, metodologias e ferramentas adotadas na prática e que norteiam a prática de desenvolvimento de soluções de software**. Os princípios se aplicam ao processo e ao produto de software se tornando em prática de desenvolvimento de software através da adoção de métodos e técnicas. Geralmente, métodos e técnicas constituem uma metodologia, as quais, são apoiadas pela utilização de ferramentas.
 
Realizar um mapeamento para identificação de vulnerabilidades e definições de prioridades para implementação de controles é uma etapa inserida dentro do planejamento de segurança da informação.

Modelo de negócio é a forma pela qual uma empresa cria valor para todos os seus principais públicos de interesse.

O processo é definido como um desenho das atividades sequenciadas geradas por entradas e que geram também saídas, apoiadas por artefatos específicos.

--