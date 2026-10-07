## Visão geral (ordem sugerida)

Os tópicos não são isolados — a ordem importa porque cada um é pré-requisito do seguinte:

1. Python e Git (base) 
2. React 
3. IA Generativa (fundamentos) 
4. Agentes
5. Avaliação de LLM/RAG 
6. Segurança e observabilidade 
7. Pesquisa/desenvolvimento de soluções (síntese prática) 
8. Relatórios executivos (transversal, praticar desde o início)

---

## 1. Python

**Curso gratuito**: Python for Everybody (Coursera/Dr. Chuck) — muito didático para quem vem do front-end
**Referência oficial**: docs.python.org/3/tutorial
**Prática orientada a projeto**: Real Python (realpython.com) — tem trilhas específicas para automação, APIs e IA
**Foco recomendado**: sintaxe básica → manipulação de dados (listas, dicts, list comprehensions) → ambientes virtuais (venv/poetry) → consumo de APIs REST (requests/httpx) → async básico (asyncio), que você vai precisar bastante em agentes de IA

## 2. React

- Como você já tem TypeScript, vá direto para **react.dev** (documentação oficial nova, com hooks e Server Components) e pule tutoriais de "JS básico"
- **Curso**: Epic React (Kent C. Dodds) ou o módulo gratuito de React em react.dev mesmo
- Foco: hooks (useState/useEffect/useContext), data fetching, integração com APIs, componentização — isso te prepara para construir interfaces que consomem LLMs (chat UIs, streaming de respostas)

## 3. IA Generativa (fundamentos)

- **Curso**: DeepLearning.AI — "Generative AI for Everyone" (Andrew Ng) para visão geral, depois "ChatGPT Prompt Engineering for Developers" e "Building Systems with the ChatGPT API"
- **Hands-on com APIs**: documentação da Anthropic (docs.claude.com) e da OpenAI (platform.openai.com/docs) — comece fazendo chamadas simples e evolua para streaming, tool use e function calling
- Fundamentos teóricos (opcional, mas ajuda a entender "por que"): Hugging Face NLP Course (gratuito, hf.co/learn)

## 4. Agentes transacionais e informacionais

Aqui a distinção prática é: **agentes informacionais** respondem perguntas/buscam informação (RAG, Q&A), **agentes transacionais** executam ações no mundo (criar um ticket, fazer uma compra, mudar um estado em um sistema) — exigem mais controle, aprovação humana e limites de autonomia.

- **Frameworks a estudar**: LangGraph (o mais usado para agentes de produção, orientado a grafo de estados) e CrewAI (mental model de "equipe de agentes com papéis", mais simples de começar)
- Vale notar que o AutoGen entrou em modo de manutenção pela Microsoft, que agora recomenda o Microsoft Agent Framework para quem começa do zero
- **Documentação**: langchain-ai.github.io/langgraph, docs.crewai.com
- **Anthropic**: guia oficial "Building Effective Agents" (anthropic.com/research) — muito bom para entender quando um agente é necessário e quando um pipeline simples resolve

## 5. Avaliação de aplicações baseadas em LLM e RAG

- **Ragas** (docs.ragas.io) é hoje o padrão de mercado para métricas de RAG — faithfulness, context precision/recall, answer relevancy
- **DeepEval** para testes no estilo pytest (bom se você quer integrar avaliação no CI)
- **Arize Phoenix** para tracing open-source baseado em OpenTelemetry, vendor-neutro
- Comece estudando o "RAG Triad": relevância da recuperação, grounding (a resposta é fiel ao contexto?) e relevância da resposta final

## 6. Segurança e observabilidade de aplicações de IA

- **OWASP Top 10 for LLM Applications (2025)** — leitura obrigatória, gratuita (owasp.org). Cobre prompt injection, vazamento de dados sensíveis, supply chain, excessive agency, vazamento de system prompt, entre outros riscos
- **Observabilidade**: Langfuse (open-source, self-hosted, bom para tracing + prompts + avaliação) ou LangSmith (se você for usar o ecossistema LangChain/LangGraph, integração praticamente nativa)
- Tema chave para 2026: "excessive agency" — como limitar o que um agente pode fazer sozinho, exigir aprovação humana para ações de risco

## 7. Pesquisa e desenvolvimento de soluções com IA

Isso é mais uma prática do que um curso único — é a habilidade de ir do problema até um protótipo funcional. Sugestão: depois de estudar os itens acima, escolha um problema real (pode até ser o app Forja) e desenvolva um mini-projeto aplicando Python + React + um agente com RAG + avaliação básica + logging. É o jeito mais eficiente de consolidar tudo.

## 8. Relatórios executivos

- Não é uma questão técnica, mas de comunicação: pratique resumir decisões técnicas em formato "situação → o que foi feito → resultado → próximos passos", sem jargão
- **Recurso**: "The Pyramid Principle" (Barbara Minto) é a referência clássica para estruturar comunicação executiva
- Dica prática: toda vez que terminar um estudo de um tópico acima, escreva um resumo de meia página como se fosse para um gestor não-técnico — isso já é o treino

## 9. Git — GitHub, GitLab ou Bitbucket

- **Fundamentos de Git**: "Pro Git" (livro gratuito, git-scm.com/book) — cobre tudo que você precisa
- **Prática**: GitHub Skills (skills.github.com) tem trilhas interativas gratuitas (pull requests, actions, colaboração)
- Diferenças entre GitHub/GitLab/Bitbucket são principalmente de CI/CD e gestão — se seu objetivo é vaga/mercado, GitHub é o mais comum no Brasil, mas GitLab tem CI/CD nativo mais robusto

---

## Roadmap: do zero até Promptfoo e Ragas

A ideia é construir uma base conceitual antes de tocar nas ferramentas — senão você decora comandos sem entender o que está medindo. Dividi em 5 etapas.

### Etapa 1 — Pré-requisitos (se já não tiver)

- Python básico (você já tem isso no radar do plano anterior) e familiaridade com chamadas de API REST
- Conceito de prompt engineering: como estruturar prompts, few-shot, system prompt
- **Fontes gratuitas**: curso "ChatGPT Prompt Engineering for Developers" (DeepLearning.AI, gratuito) ou qualquer playlist de prompt engineering do canal **IBM Technology** (inglês, vídeos curtos e bem explicados)

### Etapa 2 — O que é um "LLM eval" (conceito antes da ferramenta)

Antes de usar qualquer ferramenta, entenda por que avaliação de LLM é diferente de teste de software tradicional: a saída não é determinística, então você não compara string exata, usa critérios (contains, similaridade semântica, "llm-as-judge" — outro LLM avaliando a resposta).

- **YouTube**: busque "LLM evals explained" ou "LLM as a judge explained" — o canal **IBM Technology** e o **Prompt Engineering** (canal homônimo, bem focado nesse nicho de avaliação/RAG) têm vídeos diretos sobre isso
- Esse é o único ponto do roadmap em que vale mais entender o conceito do que ver um tutorial de ferramenta específica

### Etapa 3 — Promptfoo (avaliação de prompts/LLM em geral)

Contexto importante: a OpenAI adquiriu o Promptfoo em março de 2026, mas o projeto continua open-source (MIT) e com suporte a dezenas de provedores de LLM — então o que você aprender continua válido independente do modelo usado.

Ordem prática de estudo:

1. Instalar (`npm install -g promptfoo`) e rodar `promptfoo init` para ver a estrutura de um eval
2. Entender os 3 blocos de um config: prompts, providers (modelos) e test cases/assertions
3. Rodar seu primeiro eval com asserções simples (`contains`, `icontains`) antes de partir para `llm-rubric` (onde um LLM avalia a resposta por critério)
4. Explorar `promptfoo view` para visualizar resultados em matriz comparando modelos

- **Fonte gratuita principal**: a própria documentação oficial em **promptfoo.dev/docs** tem um "Getting Started" muito direto, com exemplos prontos para copiar
- **YouTube**: busque "Promptfoo tutorial 2026" — o canal **Prompt Engineering** costuma cobrir ferramentas assim que ficam relevantes; como é uma ferramenta nova, prefira vídeos dos últimos meses

### Etapa 4 — Fundamentos de RAG (antes de avaliar RAG)

Para o Ragas fazer sentido, você precisa entender o pipeline de RAG: retrieval (busca em base vetorial) → generation (LLM usa o contexto recuperado para responder).

- Revise o módulo de RAG que já estava no seu plano anterior (Hugging Face NLP Course ou vídeos do IBM Technology sobre "what is RAG")

### Etapa 5 — Ragas (avaliação específica de RAG)

Em 2026, o Ragas é descrito como o framework padrão para avaliação de RAG, com abordagem "reference-free" — a maior parte das métricas não exige que você escreva uma resposta-gabarito para cada pergunta, o que acelera bastante a criação da primeira baseline.

Ordem prática de estudo:

1. `pip install ragas` e entender os 4 objetos centrais: pergunta, contextos recuperados, resposta gerada, e (opcionalmente) uma referência
2. Métrica mais importante para começar: **faithfulness** (a resposta é fiel ao contexto recuperado, sem "alucinar"?)
3. Depois: **context precision/recall** (a busca recuperou os documentos certos?) e **answer relevancy** (a resposta responde à pergunta?)
4. Montar um dataset de avaliação pequeno (`EvaluationDataset`/`SingleTurnSample`) e rodar `evaluate()` com 2-3 métricas antes de ir para o conjunto completo

- **Fonte gratuita principal**: **docs.ragas.io** tem quickstart com código rodável
- Se quiser entender a motivação teórica, o paper original está livre no arXiv (arXiv:2309.15217) — não é essencial, mas ajuda a entender por que as métricas foram desenhadas daquele jeito
- **YouTube**: busque "Ragas tutorial RAG evaluation" — de novo, prefira vídeos de 2026 já que a lib evolui rápido; canais como **Prompt Engineering** e **Sam Witteveen** costumam ter esse tipo de conteúdo hands-on

### Depois disso

Com Promptfoo (avaliação geral de prompts/modelos) e Ragas (avaliação específica de RAG) dominados, o próximo passo natural — que já estava no seu plano anterior — é conectar isso a observabilidade (Langfuse/Arize Phoenix) para rodar essas avaliações continuamente, não só manualmente.