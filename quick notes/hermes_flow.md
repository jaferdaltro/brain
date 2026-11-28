## Configuração — 28/11/2026

- Hermes Agent: versão 0.23.4.
    
- Plugin: Advanced Delegation 1.2.0.
    
- Modo de delegação: Profile Routes.
    
- Ferramenta: delegate_task.
    
- Agente auxiliar padrão: OpenAI.
    

## Equipe de agentes

### Hermes principal — Orquestrador

- Provedor: OpenRouter.
    
- Responsabilidades: coordenar agentes, distribuir tarefas e consolidar resultados.
    
- Comando: `hermes -p default chat`
    

### OpenAI — Estrategista

- Modelo: gpt-6.2-sol.
    
- Reasoning Effort: Medium.
    
- Responsabilidades: planejamento estratégico, análise de negócios e resolução de problemas.
    
- Comando: `hermes -p openai chat`
    

### Codex — Engenheiro de software

- Modelo: gpt-6.2-sol.
    
- Reasoning Effort: High.
    
- Responsabilidades: desenvolvimento, arquitetura, revisão de código e testes.
    
- Comando: `hermes -p codex chat`
    

### Scraper — Pesquisador

- Responsabilidades: pesquisa de mercado, prospecção de clientes e coleta de dados públicos.
    
- Comando: `hermes -p scraper chat`
    

## Configuração de delegação

`hermes -p default delegation config`

## Próximos passos

- Validar um projeto completo envolvendo todos os agentes.
    
- Testar a seleção automática dos especialistas.
    
- Desenvolver fluxos de trabalho para prospecção de clientes.
    

Tags: #hermes #agentes-ia #automacao #openai #codex

Salve a nota em uma pasta temática adequada dentro do Vault Brain. Não sobrescreva notas existentes nem altere outros arquivos. Confirme a criação da nota e informe seu caminho completo.