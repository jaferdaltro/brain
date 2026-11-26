---
title: "Build an Always-On AI Scraping Agent with Hermes + Oxylabs"
channel: "Oxylabs"
url: "https://www.youtube.com/watch?v=yv7PDbVb0Ww"
date: "2024"
video_id: "yv7PDbVb0Ww"
tags: [HermesAgent, AI, Scraping, Oxylabs, VPS, Slack, Automation, Agent, SelfImproving]
---

# Build an Always-On AI Scraping Agent with Hermes + Oxylabs

**URL:** https://www.youtube.com/watch?v=yv7PDbVb0Ww
**Canal:** Oxylabs
**Apresentador:** Mantvydas

---

## 📋 Resumo Executivo

Vídeo tutorial completo mostrando como construir um **agente de scraping sempre ativo** usando **Hermes Agent** (framework open-source da Nous Research) + **Oxylabs Web Scraper API** + **Slack** como canal de entrega. O agente roda em VPS, aprende sozinho (salva skills), agenda jobs e entrega resultados no Slack.

---

## 🏗️ Arquitetura da Solução

| Componente | Papel |
|------------|-------|
| **Hermes Agent** | Framework do agente (memória, skills loop, CLI, gateways) |
| **Claude Opus 4.6** | LLM / cérebro (via Anthropic) |
| **VPS Hostinger KVM2** | Infraestrutura (2 cores, 8GB RAM, sempre ligado) |
| **Oxylabs Web Scraper API** | Camada de infra: CAPTCHAs, JS rendering, proxy rotation |
| **Slack** | Canal de entrega (gateway + Socket Mode) |
| **Cron/Hermes Scheduler** | Agendamento (ex: toda segunda 9h) |

---

## 🔑 Três Diferenciais do Hermes

1. **Memória Persistente** — lembra contexto entre sessões
2. **Self-Improving Skills Loop** — salva abordagens que funcionam como skills reutilizáveis (padrão SKILL.md)
3. **Multi-Surface + Scheduling** — Slack, Telegram, email + jobs agendados

---

## 🛠️ Passos do Build

### 1. VPS (Hostinger KVM2 - 2 cores, 8GB RAM)
- Ubuntu, usuário dedicado `hermes` (não root)
- SSH key, sudo, atualizações

### 2. Instalação Hermes
```bash
# One-liner installer (full setup)
# Escolhas: Anthropic → API Key → Claude Opus 4.6 → Terminal local
```

### 3. Gateway Slack
- `hermes slack manifest write` → JSON manifest
- `api.slack.com/apps` → From manifest → Create
- Tokens: **xapp-** (App-Level, connections:write) + **xoxb-** (Bot User OAuth)
- `hermes gateway setup` → Slack → tokens + allowed users (Slack Member ID)
- `hermes gateway install` + `hermes gateway status`

### 3. Scraping Nativo (falha)
- Hermes + browser tools → CAPTCHA, JS rendering, IP reputation
- **Problema:** infraestrutura, não prompt

### 4. Oxylabs Web Scraper API (fix)
- Credenciais no `.env`: `OXYLABS_USERNAME`, `OXYLABS_PASSWORD`
- Source: Amazon product (ASIN, auto-parse=true)
- Mesmo prompt funciona no CLI e Slack

### 5. Skills Loop (Self-Improving)
- "Save as skill" → gera `SKILL.md` em `skills/`
- Próxima vez: chama skill por nome em vez de redescobrir
- Padrão aberto: `agentskills.io`

### 6. Scheduling
- "Run this skill every Monday at 9 AM"
- Hermes cria job, entrega no Slack

---

## ⚠️ Segurança & Boas Práticas

| Risco | Mitigação |
|-------|-----------|
| Terminal access (root) | Usuário dedicado, VPS isolado |
| API keys/tokens vazando | `.env` no VPS, nunca em prompts |
| Prompt injection | Blast radius contido no VPS |
| Acesso excessivo | Princípio do menor privilégio |

**Regra:** Trate o agente como "novo contratante com chaves do prédio" — só dê acesso ao que o job precisa.

---

## 📜 Legal & Ética (Scraping)

- Verifique **Terms of Service** do site alvo
- Respeite **robots.txt**
- Dados públicos ≠ livres de regulação
- **Delay** entre requests, respeite rate limits
- **Cache** resultados (não re-scrape diário)

---

## 🔗 Links Úteis

- [Hermes Agent Docs](https://hermes-agent.nousresearch.com/docs)
- [Oxylabs Web Scraper API](https://oxylabs.io/products/web-scraper-api)
- [agentskills.io](https://agentskills.io) — biblioteca de skills
- [Hostinger VPS](https://hostinger.com) (link tracked na descrição)

---

## 🏷️ Tags

#HermesAgent #Oxylabs #Scraping #AI #Automation #VPS #Slack #Agent #SelfImproving #NousResearch