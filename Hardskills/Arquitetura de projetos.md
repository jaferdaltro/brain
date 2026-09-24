
## Como abordar "fale sobre a arquitetura de um projeto seu"

**1. Contexto antes da técnica** Comece explicando o problema de negócio e a escala (usuários, requisições/dia, tamanho do time) — isso justifica as decisões que você tomou depois. Recrutadores técnicos gostam de ver que você pensa em trade-offs, não só em tecnologia pela tecnologia.

**2. Estrutura sugerida (formato STAR adaptado pra arquitetura)**

- **Situação**: qual sistema, qual dor ele resolvia
- **Decisões**: monolito vs. microsserviços, sync vs. async, banco relacional vs. NoSQL — e _por quê_
- **Trade-offs**: o que você sacrificou (ex: simplicidade vs. escalabilidade)
- **Resultado**: métricas concretas (latência, uptime, redução de custo)

**3. Pontos fortes pra você explorar, dado seu perfil**

- Fale sobre decisões de CI/CD: como estruturou pipelines, gates de qualidade (RuboCop entra bem aqui como parte de "qualidade de código automatizada")
- PostgreSQL avançado: índices, particionamento, query tuning — mostra profundidade além do básico do Rails
- Docker/AWS: como você pensa em ambientes (dev/staging/prod), infraestrutura como código, containerização de serviços Rails

**4. Perguntas comuns que costumam vir depois**

- "Como você garantiria que essa arquitetura escala?"
- "O que você mudaria se tivesse que refazer?"
- "Como decidiu entre X e Y?" (sempre tenha 2-3 alternativas que você considerou e descartou, com motivo)

**5. Erro comum a evitar** Não caia em listar tecnologias sem explicar o _porquê_. Entrevistador de arquitetura quer ver raciocínio, não currículo falado.

Quer que eu monte um roteiro específico baseado em algum projeto seu (ex: a simulação de arquitetura que você mencionou trabalhar, ou algo com CI/CD)? Posso ajudar a estruturar a narrativa completa.