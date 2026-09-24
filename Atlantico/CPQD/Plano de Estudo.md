## Visão geral (ordem sugerida)

Os tópicos não são isolados — a ordem importa porque cada um é pré-requisito do seguinte:

1. Python e Git (base) → 2. React → 3. IA Generativa (fundamentos) → 4. Agentes → 5. Avaliação de LLM/RAG → 6. Segurança e observabilidade → 7. Pesquisa/desenvolvimento de soluções (síntese prática) → 8. Relatórios executivos (transversal, praticar desde o início)

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
- - **Asimov Academy** (PT-BR) — tem trilha específica de "Agentes de IA" do básico ao avançado, além de IA generativa com Hugging Face
- **IBM Technology** (inglês) — ótimos vídeos curtos explicando conceitos (RAG, embeddings, fine-tuning) de forma visual
- **Andrej Karpathy** (inglês) — se quiser entender o "motor por baixo do capô" dos LLMs, é o canal mais respeitado tecnicamente, embora mais denso

## 4. Agentes transacionais e informacionais

Aqui a distinção prática é: **agentes informacionais** respondem perguntas/buscam informação (RAG, Q&A), **agentes transacionais** executam ações no mundo (criar um ticket, fazer uma compra, mudar um estado em um sistema) — exigem mais controle, aprovação humana e limites de autonomia.

- **Frameworks a estudar**: LangGraph (o mais usado para agentes de produção, orientado a grafo de estados) e CrewAI (mental model de "equipe de agentes com papéis", mais simples de começar)
- Vale notar que o AutoGen entrou em modo de manutenção pela Microsoft, que agora recomenda o Microsoft Agent Framework para quem começa do zero
- **Documentação**: langchain-ai.github.io/langgraph, docs.crewai.com
- **Anthropic**: guia oficial "Building Effective Agents" (anthropic.com/research) — muito bom para entender quando um agente é necessário e quando um pipeline simples resolve
- **Sam Witteveen** e **James Briggs** (inglês) — ambos têm playlists extensas sobre LangGraph, CrewAI e padrões de agentes, muito hands-on
- **Asimov Academy** (PT-BR) — trilha de agentes citada acima

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

Consegui achar boas opções para cada tópico — misturando canais em português e inglês (a área de IA ainda tem mais conteúdo de qualidade em inglês, mas você pega tranquilo com legendas):

## Python

- **Asimov Academy** (PT-BR) — hoje é a referência nacional para Python aplicado a IA: tem playlists de "Python para IA", LangChain, agentes e projetos práticos como leitura de PDF com RAG
- **Dunossauro** (Eduardo Mendes, PT-BR) — conteúdo mais avançado (corrotinas, FastAPI, Django), lives semanais
- **Corey Schafer** (inglês) — referência clássica para fundamentos sólidos de Python

## React

- **Rocketseat** (PT-BR) — playlist de React bem completa e didática, cobre também Node e TypeScript
- **Lucas Montano** (PT-BR) — foco forte em React e novidades do ecossistema
- **Codevolution** ou **Web Dev Simplified** (inglês) — explicações curtas e diretas de hooks, TypeScript com React

## IA Generativa / LLMs

- **Asimov Academy** (PT-BR) — tem trilha específica de "Agentes de IA" do básico ao avançado, além de IA generativa com Hugging Face
- **IBM Technology** (inglês) — ótimos vídeos curtos explicando conceitos (RAG, embeddings, fine-tuning) de forma visual
- **Andrej Karpathy** (inglês) — se quiser entender o "motor por baixo do capô" dos LLMs, é o canal mais respeitado tecnicamente, embora mais denso

## Agentes transacionais e informacionais

- **Sam Witteveen** e **James Briggs** (inglês) — ambos têm playlists extensas sobre LangGraph, CrewAI e padrões de agentes, muito hands-on
- **Asimov Academy** (PT-BR) — trilha de agentes citada acima

## Avaliação de LLM/RAG e observabilidade

Esse é o ponto mais fraco em português — a maior parte do conteúdo bom ainda está em inglês:

- **Canal oficial do LangChain no YouTube** — tem vídeos específicos sobre avaliação com LangSmith e RAG
- Buscar diretamente por "Ragas tutorial" ou "Arize Phoenix tutorial" no YouTube costuma trazer vídeos curtos e atualizados direto dos mantenedores das ferramentas

## Segurança de aplicações de IA

- Pouco conteúdo dedicado em vídeo — o próprio site da OWASP e leituras continuam sendo a fonte mais confiável aqui. Vale buscar "OWASP Top 10 LLM explained" no YouTube para achar resumos em vídeo

## Git

- **Curso em vídeo do GitHub Skills** ou qualquer playlist de "Git e GitHub" da Rocketseat/Código Fonte TV (PT-BR) cobrem bem o essencial

---

Uma dica prática: para os tópicos mais recentes (agentes, avaliação de RAG, observabilidade), prefira sempre filtrar por vídeos publicados nos últimos 6 meses — essa área muda muito rápido e tutorial de 2024 já pode estar desatualizado.