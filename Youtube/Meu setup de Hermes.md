---
title: "Como eu uso o Hermes Agent no dia a dia"
channel: "Bruno Camargo (Pixel Educação)"
url: "https://www.youtube.com/watch?v=TSimMWwR6to"
date: "Agosto 2026"
video_id: "TSimMWwR6to"
tags: [HermesAgent, IA, Agentes, Automação, SegundoCérebro, GitHub, VPS, BrunoCamargo, PixelEducação, Produtividade]
---

# Como eu uso o Hermes Agent no dia a dia — Bruno Camargo

**URL:** https://www.youtube.com/watch?v=TSimMWwR6to
**Data:** Agosto 2026
**Canal:** Bruno Camargo (Pixel Educação)

---

## 📋 Resumo Executivo

Bruno Camargo mostra como usa o **Hermes Agent** self-hosted em VPS para gerenciar múltiplos negócios, criar conteúdo e organizar vida pessoal. Arquitetura baseada em **Second Brain no GitHub**, **squad de agentes** e **skills conscientes**.

---

## 🏗️ Arquitetura de Agentes (Squad)

| Agente | Função | Sub-agentes / Características |
|--------|--------|------------------------------|
| **Amora Boss** | Mestre — gerencia negócios, finanças, contratos, alunos | Orquestra sub-agentes on-demand |
| **Dexter** | Criação de conteúdo | Pesquisa trends, analisa virais, carrosséis, assiste vídeos (Gemini), gera vídeo (Higgs Field) |
| **Amora Daredevil (Pessoal)** | Finanças, viagens, saúde, família, logística | Bancos via MCP, alertas promoções, grupo com esposa |

---

## ☁️ Infraestrutura

- **VPS:** Hostinger KVM 2 (8GB RAM, 100GB SSD) — ~R$30/mês (24 meses + cupom)
- **RAM por agente:** ~2.5 GB → comporta 3-4 agentes
- **Second Brain:** GitHub (um cérebro por agente/empresa), não Obsidian
- **Estrutura de pastas:** `mapa.md` (índice), `ledger` (sumário diário contexto)
- **Permissionamento:** VPS = casa com quartos; Cérebro = pastas por nível de acesso

---

## 💬 WhatsApp & Grupos

- Amora lê grupos (suporte, vendas, mentoria) como **radar**
- Identifica oportunidades de manifestação, executa ações, extrai métricas/dados
- Grupo "Organização" com esposa

---

## 🖥️ App Hermes (Desktop)

- **Velocidade:** Grok = resposta quase instantânea
- **Layouts flexíveis:** sessões paralelas, side chats
- **Bots:** sub-agentes com *souls* (personalidades) e tools/MCPs próprios, cérebro compartilhado
  - *Amora Crítica* — análise cirúrgica, sabatina ideias, review PRD
  - *Amora Designer* — UI/branding, sistema visual, fontes, cores
- **Background work:** "By the way" executa sem interromper tarefa principal
- **Gateway:** Conecta VPS via SSH + Tailscale (Hermes Remote)
- **Update:** "Update all instances" sincroniza local + VPS

---

## 🤖 LLMs Utilizadas

| LLM | Uso |
|-----|-----|
| **Grok** | Principal — velocidade extrema |
| **Qwen 3.8** (OpenRouter) | Surpreendeu positivamente, bom custo-benefício |
| **Gemini 3.0 Flash** | Assistir vídeos (Dexter) |
| **Claude / Codex** | Desktop work (não agente) |

---

## ⚙️ Automações Reais (Exemplos)

### Financeiro / Backoffice (Amora Boss)
- Emite NFe, revisa contratos, fluxo de caixa (Omie API)
- Conecta prefeituras, faturas cartão → contador automático
- **Contratos:** Skill análise → identifica red/yellow flags → envia p/ Autentique p/ assinatura

### Hotmart API (Gestão Alunos)
- Jornada de alunos, % avanço por etapa
- Identifica onde travam, conteúdo não visto

### Pessoal (Amora Daredevil)
- **Bancos:** MCP nativo → finanças
- **Carro:** Alertas promoções, insights Twitter (BYD King vs Song)
- **Viagens/Saúde/Filhos:** Logística completa

### Conteúdo (Dexter)
- Pesquisa benchmarks diários
- Analisa virais → extrai hooks, CTAs, formatos
- Cria carrosséis (skill complexa)
- Métricas tempo real redes sociais

---

## 🧠 Filosofia / Lições Aprendidas

1. **Contexto é Rei** — Tudo vai pro agente (WhatsApp, email, calendário, áudios offline, gravações médicas). Quanto mais contexto, melhor performa.

2. **Menos é Mais** — 1 agente mestre + sub-agentes on-demand = menos manutenção. Agentes conversam entre si (@AmoraCrítica).

3. **Tudo vira Skill Consciente** — Mesmo com auto-learning do Hermes, crie skills deliberadamente. Peça mapas de skills, dashboards.

4. **Criatividade > Conhecimento Técnico** — Encaixar agente na vida/negócio importa mais que saber Python. Técnico ajuda 0→2, criatividade leva 2→5.

5. **Zero Fanatismo por Empresa** — Usa o que resolve:
   - Codex → limite alto
   - Grok → automação empresa
   - Claude → desktop work
   - Hermes → agente autônomo

---

## 🔗 Links Úteis (mencionados no vídeo)

- VPS Hostinger + cupom (descrição do vídeo)
- Instalador Hermes Pixel Educação (~R$30 — deploy completo: Telegram, agente configurado, VPS)
- Ledger (sumário diário contexto) — vídeo recente no canal
- Brain no GitHub (estrutura de pastas, mapa.md)