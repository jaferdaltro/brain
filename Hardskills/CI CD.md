Video Aula
https://www.youtube.com/watch?v=Iz2inol7f1k&t=633s 
## Conceitos fundamentais

**CI (Integração Contínua)**

- Integrar código com frequência (idealmente várias vezes ao dia) numa branch compartilhada
- Build automatizado + testes rodando a cada commit/PR
- Objetivo: pegar conflitos e bugs cedo, evitar "integration hell"

**CD (Entrega vs Implantação Contínua)**

- **Continuous Delivery**: código sempre pronto pra ir pra produção, mas o deploy final é manual (um clique)
- **Continuous Deployment**: todo commit que passa nos testes vai automaticamente pra produção, sem intervenção humana
- Saber diferenciar os dois é um clássico pega-quem-decorou-buzzword

## Pontos técnicos que costumam cair

- **Pipeline stages**: build → test → lint/security scan → deploy (staging → produção)
- **Testes na pipeline**: unitários rodam rápido e cedo; integração/e2e mais tarde ou em paralelo
- **Estratégias de deploy**: blue-green, canary, rolling deployment — e quando usar cada uma
- **Rollback**: como reverter rápido se algo quebra em produção
- **Feature flags**: desacoplar deploy de release
- **Artefatos e versionamento**: builds imutáveis, tags/semver
- **Secrets management**: nunca credenciais hardcoded no pipeline
- **Idempotência e reprodutibilidade**: pipeline deve dar o mesmo resultado sempre

## Perguntas comportamentais comuns

- "Conte sobre uma vez que um pipeline quebrou em produção — o que você fez?"
- "Como você reduziria o tempo de build de uma pipeline lenta?"
- "Qual a diferença entre uma pipeline com testes flaky e uma confiável, e como lidar com isso?"

## Ferramentas

Vale saber comparar pelo menos superficialmente: GitHub Actions, GitLab CI, Jenkins, CircleCI — o entrevistador geralmente quer ver que você entende os conceitos por trás, não decoreba de sintaxe.


## Azure

Azure é a plataforma de cloud computing da Microsoft, lançada em 2010. É a segunda maior do mercado (atrás só da AWS), com forte adoção em empresas que já usam produtos Microsoft (Windows Server, Active Directory, SQL Server, .NET).

## Categorias principais de serviços

**Computação**

- **Virtual Machines** — equivalente ao EC2
- **App Service** — PaaS pra hospedar web apps/APIs sem gerenciar infra (parecido com Elastic Beanstalk)
- **Azure Functions** — serverless, equivalente ao Lambda
- **AKS (Azure Kubernetes Service)** — Kubernetes gerenciado, equivalente ao EKS
- **Container Apps** — pra rodar containers sem gerenciar cluster

**Armazenamento e banco de dados**

- **Blob Storage** — equivalente ao S3
- **Azure SQL Database** — SQL Server gerenciado
- **Cosmos DB** — banco NoSQL multi-modelo, bem forte tecnicamente (multi-region, baixa latência)
- **PostgreSQL/MySQL flexible server** — bancos gerenciados, já que você mexe com Postgres

**Redes**

- **Virtual Network (VNet)** — equivalente à VPC
- **Azure Load Balancer / Application Gateway**
- **Azure Front Door / CDN**

**Identidade**

- **Entra ID (ex-Azure AD)** — gerenciamento de identidade, muito forte em ambientes corporativos com SSO/AD

**DevOps**

- **Azure DevOps** — suite com Boards, Repos, Pipelines, Artifacts (concorrente do GitHub, aliás a Microsoft é dona do GitHub também)
- **Azure Pipelines** — CI/CD nativo, alternativa ao GitHub Actions/Jenkins que você já estuda

## Diferenças de mentalidade vs AWS

- Terminologia diferente pra conceitos parecidos (Resource Group ≈ organização de recursos, não tem equivalente direto na AWS)
- Integração nativa muito forte com ferramentas Microsoft (Office 365, Power BI, Dynamics)
- Modelo de billing e regras de rede/VNet têm particularidades próprias — vale não tentar "traduzir" 1:1 da AWS

## Quando aparece em entrevistas

Geralmente querem ver se você entende os conceitos de cloud de forma agnóstica (IaaS vs PaaS vs SaaS, escalabilidade, alta disponibilidade) e consegue mapear pra qualquer provedor — não decoreba de nomes de serviço.

# Estratégias de deploy
## Recreate (a mais simples)

- Derruba tudo da versão antiga, depois sobe a nova
- **Downtime**: sim, total
- Quando usar: ambientes de dev/teste, ou apps onde downtime não é problema
- Vantagem: simples, barato, sem complexidade de infra

## Rolling Deployment

- Substitui as instâncias antigas pelas novas gradualmente, uma (ou um grupo) por vez
- **Downtime**: zero (se bem configurado)
- Rollback: mais lento, porque tem que reverter instância por instância
- Cuidado: durante a transição, você tem duas versões rodando ao mesmo tempo — precisa garantir compatibilidade (principalmente de banco de dados/API)

## Blue-Green Deployment

- Mantém dois ambientes idênticos: "Blue" (produção atual) e "Green" (nova versão)
- Deploy vai pro Green, testa lá, depois só troca o roteamento/load balancer pra apontar pro Green
- **Rollback**: instantâneo — só aponta de volta pro Blue
- Trade-off: custo dobrado de infra (ainda que temporário), e migrações de banco de dados complicam (schema precisa ser compatível com as duas versões durante a transição)

## Canary Deployment

- Libera a nova versão pra uma fatia pequena de usuários (ex: 5%), monitora métricas, e vai aumentando gradualmente
- **Vantagem**: detecta problemas com blast radius pequeno, antes de afetar todo mundo
- Exige: boa observabilidade (métricas, logs, alertas) pra decidir se continua ou faz rollback
- Muito usado em empresas grandes (Google, Netflix) — é considerado "estado da arte" em entrevistas

## Feature Flags / Toggles

- Não é bem uma estratégia de deploy, mas anda junto: você faz deploy do código "desligado" e ativa via flag depois, sem novo deploy
- Desacopla **deploy** (código em produção) de **release** (funcionalidade visível pro usuário)
- Muito citado como boa prática em entrevistas seniores

## A/B Testing Deployment

- Parecido com canary, mas o objetivo é comparar comportamento/métricas de negócio entre versões, não só validar estabilidade técnica

## Tabela mental pra entrevista

|Estratégia|Downtime|Custo infra|Rollback|Complexidade|
|---|---|---|---|---|
|Recreate|Sim|Baixo|Lento|Baixa|
|Rolling|Não|Baixo|Médio|Média|
|Blue-Green|Não|Alto (2x)|Instantâneo|Média-alta|
|Canary|Não|Médio|Rápido|Alta|

Uma pergunta que gosta de aparecer: **"como você lidaria com uma migração de banco de dados num deploy blue-green ou canary?"** — a resposta esperada geralmente envolve migrações backward-compatible (expand-and-contract pattern): primeiro adiciona a coluna/campo novo sem remover o antigo, faz o deploy, depois só remove o antigo numa migração posterior.

Quer que eu monte um exemplo prático de pipeline com uma dessas estratégias (tipo GitHub Actions fazendo canary ou blue-green)?