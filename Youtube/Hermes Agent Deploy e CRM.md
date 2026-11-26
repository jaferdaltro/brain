---
title: "Hermes Agent — Deploy, Setup e CRM com Supabase (Tutorial Prático)"
channel: "Não identificado no transcrição"
url: "https://www.youtube.com/watch?v=W_ZgH0WPayo"
date: "2026"
video_id: "W_ZgH0WPayo"
tags: [HermesAgent, IA, Agentes, Automação, Supabase, CRM, Deploy, OpenRouter, DeepSeek, VPS, Railway, MCP, SegundoCérebro, Produtividade]
---

# Hermes Agent — Deploy, Setup e CRM com Supabase (Tutorial Prático)

**URL:** https://www.youtube.com/watch?v=W_ZgH0WPayo
**Canal:** Não identificado no transcrição
**Data:** 2026

---

## 📋 Resumo Executivo

Tutorial prático e completo mostrando como fazer deploy do **Hermes Agent** (framework de IA autônomo da Nous Research) em instância própria, configurar provedor LLM (OpenRouter + DeepSeek), conectar ao Telegram e estender a plataforma construindo um **CRM personalizado com Supabase** via MCP server.

---

## 🏗️ O que é o Hermes Agent

| Característica | Detalhe |
|----------------|---------|
| **Licença** | MIT (gratuito, sem assinatura, sem limites de uso) |
| **Execução** | Local ou VPS, 24/7 |
| **Canais de acesso** | Telegram, Discord, Slack, Email |
| **Capacidades** | Criar arquivos, buscar web, rodar código, navegar sites |
| **Extensibilidade** | Modelo de skills autônomo (auto-aprimoramento) |
| **Estrelas no GitHub** | 116.000+ |

---

## 🔄 Loop de Auto-Aprimoramento (Self-Improving)

O Hermes difere de projetos como o OpenClaw (345K estrelas) por ter um **fechamento de loop contínuo**:

1. **Criação de skill** — Após cada tarefa, o agente pergunta: *"O que aprendi vale a pena guardar?"* Se sim, escreve uma skill (procedimento reutilizável persistente).
2. **Refinamento de skill** — Quando encontra abordagem melhor, atualiza a skill existente. Elas evoluem com o uso, não são estáticas.
3. **Nudge periódico** — A cada 15 chamadas de ferramenta, pausa para decidir o que salvar na memória. Ciclo de reflexão integrado, não apenas limpeza no final da tarefa.
4. **Modelagem do usuário** — Constrói modelo de quem você é, preferências, estilo de comunicação e metas ("RL on user preferences"). Aprende o usuário, não apenas as tarefas.

Tudo persiste entre sessões e alimenta a próxima execução. Quanto mais você usa, melhor fica.

---

## 🚀 Deploy Passo a Passo

### 1. Deploy na VPS / Railway
- Usar template de one-click deploy (link na descrição)
- Criar instância sandbox
- Definir admin username/password (ex: admin/admin)
- Salvar, configurar, deployar
- Aguardar alguns minutos para ficar pronto

### 2. Configuração Inicial (Console de Setup)
- Acessar URL da instância
- Fazer login com credenciais admin
- **Selecionar provedor LLM:** OpenRouter (no exemplo)
- Criar API key na OpenRouter e colar no setup
- **Modelo escolhido:** DeepSeek V4 Flash (via OpenRouter)
  - Custo: 14 centavos/milhão input tokens, 28 centavos/milhão output tokens
  - Cache read: 2 centavos/milhão tokens (quando já está na memória do LLM)
  - Provedor mais rápido: selecionar "nitro"

### 3. Conectar Telegram
- Já ter token do bot configurado
- Colar token no setup do Hermes
- Salvar e iniciar
- No dashboard, verificar que o gateway está rodando
- No Telegram: /start → gera código de pareamento
- Voltar ao dashboard Hermes → Setup → Users → Aprovar
- Agora pode conversar com o bot

### 4. Adicionar MCP Server (Supabase)
- Criar projeto no Supabase (free tier suficiente)
- Nomear projeto: "Hermes"
- Definir senha, criar projeto
- Gerar access token (nome: "Hermes Agent")
- No Telegram: dizer ao Hermes "quero adicionar um MCP server"
- Colar URL do Supabase + access token
- Autorizar e adicionar a capacidade
- Reiniciar o agente para pegar a mudança

---

## 📊 Exemplo Prático: CRM com Supabase

Após conectar o MCP do Supabase, o usuário testa via linguagem natural:

| Comando | Resultado |
|---------|-----------|
| "Criar tabela contacts com colunas: name, email, company, deal size" | Tabela criada via MCP no Supabase |
| "Adicionar estes contatos" (nomes e deal sizes) | 3 linhas populadas; confirmação ao atualizar tabela no Supabase |
| "Mover deal do Marcus Johnson de new para negotiation" | Atualizado e confirmado |
| "Mostrar todos os deals acima de 40K ordenados por deal size" | Hermes gera e executa SQL nos bastidores |

### Auto-aprimoramento em ação
Após algumas interações, o Hermes pergunta se o usuário quer criar uma nova skill para usar o Supabase. Se sim, ele **cria autonomamente a skill "Supabase MCP scripts"** baseada na reflexão sobre como melhorar o processo. Essa skill é usada automaticamente em interações futuras com aquele dado.

---

## ⏰ Automação / Agendamento

Exemplo configurado no vídeo:
- **Lembrete às 9:00 da manhã** sobre contatos não alcançados há 14 dias
- O scheduler roda todo dia às 9h, consulta o Supabase e envia mensagem
- Configurável via dashboard Hermes → Cron

---

## 💰 Custo Estimado (Mensal)

| Componente | Custo |
|------------|-------|
| Hermes Agent | Gratuito (MIT) |
| LLM (DeepSeek V4 Flash via OpenRouter) | ~US$ 5/mês |
| Hospedagem (Railway) | ~US$ 5/mês (cobrado apenas quando ativo) |
| Banco de dados (Supabase free tier) | Gratuito (500 MB DB, 1 GB file storage, 50.000 MAU, requests ilimitadas) |
| **Total** | **~US$ 10/mês** |

É menos que uma assinatura do ChatGPT Plus, para um assistente 24/7 que gerencia dados reais, aprende padrões e roda automações enquanto você dorme.

---

## ⚠️ Pontos de Atenção (Gotchas)

- Hermes é público há ~2 meses, ainda em **V0.x**
- Sete releases nos últimos 27 dias — pode quebrar entre atualizações
- Ecossistema ainda em estágio inicial
- **Porém:** o core (learning loop, memória, integração MCP) já é sólido e melhora rápido
- Indicado para quem está confortável em estar na "ponta de lança" de algo que amadurece rapidamente

---

## 🔗 Links Úteis (descrito na descrição do vídeo)

- Repositório do Hermes Agent
- Template de deploy one-click no Railway
- Setup MCP do Supabase
- Templates de configuração
- Guia escrito de configuração do gateway Telegram (linkado na descrição)

---

## 🏷️ Tags

#HermesAgent #IA #Agentes #Automação #Supabase #CRM #MCP #Deploy #OpenRouter #DeepSeek #VPS #Railway #Telegram #Produtividade #AutoAprimoramento