
## Conceitos fundamentais

- Diferença entre `git merge` e `git rebase` — quando usar cada um
- O que é um conflito de merge e como resolver
- Diferença entre `git fetch` e `git pull`
- O que é o "staging area" (index) e por que ele existe
- Diferença entre `HEAD`, branch e tag

## Fluxo de trabalho e branching

- Estratégias de branching: Git Flow, GitHub Flow, Trunk-Based Development — vantagens e desvantagens de cada
- Como você estrutura branches em uma equipe (feature branches, release branches, hotfixes)
- O que é um "detached HEAD" e como sair dessa situação
- Squash commits: quando faz sentido e quando não

## Comandos e cenários práticos

- Como reverter um commit já enviado (`revert` vs `reset`) e a diferença de impacto em histórico compartilhado
- Como recuperar um commit perdido (`reflog`)
- Como usar `cherry-pick` e em que situação
- `git bisect` para encontrar o commit que introduziu um bug
- Como resolver um `rebase` interrompido por conflitos

## Nível sênior / arquitetura

- Como você define uma política de code review e branch protection
- Como lida com repositórios monolíticos gigantes (monorepo) vs multi-repo, submodules vs subtree
- Como integra controle de versão com CI/CD (triggers por branch, tags para deploy, versionamento semântico)
- Como estruturar commits para facilitar rollback automatizado em pipelines
- Assinatura de commits (GPG) e por que isso importa em ambientes regulados
- Como lidar com segredos commitados por engano (remoção de histórico, `git filter-repo`)

## Perguntas comportamentais/situacionais

- "Conte sobre uma vez que um merge quebrou a produção — o que você fez?"
- "Como você convence um time a adotar convenções de commit (Conventional Commits, por exemplo)?"
- "Como você lida com desenvolvedores que dão commit direto na main?"

Quer que eu monte um roteiro de estudo focado nas perguntas mais prováveis pro seu nível (sênior), ou prefere simular uma entrevista com perguntas e eu avaliar suas respostas?