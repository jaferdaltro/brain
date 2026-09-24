# Fluxo do Usuário — App de Treino Personalizado

## 1. Boas-vindas
- Splash screen com logo/animação
- Tela de apresentação rápida (1-3 slides) mostrando o diferencial: "monte seu treino com os equipamentos que você tem"

## 2. Cadastro / Login
- Criar conta (e-mail/senha ou login social)
- Opção "continuar sem conta" (modo convidado) se quiser reduzir fricção — dados ficam locais até criar conta

## 3. Coleta de dados do usuário
Tela em etapas (stepper), uma pergunta por tela para não intimidar:
- Peso
- Altura
- Idade
- Sexo
- (opcional) Nível de experiência: iniciante / intermediário / avançado

## 4. Rotina de treino
- Quantos dias por semana vai treinar (2 a 6)
- Duração desejada por sessão (ex: 30, 45, 60, 90 min)
- Objetivo (opcional, mas ajuda muito no algoritmo): hipertrofia, emagrecimento, condicionamento, força

## 5. Seleção de equipamentos disponíveis
- Grid visual com cards de imagem (halteres, barra, banco, máquinas, cabo, elástico, peso do corpo, etc.)
- Toque para selecionar/desselecionar (feedback visual: borda colorida + check)
- Botão "Selecionar tudo" para quem treina em academia completa

## 6. Geração do treino
- Tela de loading com alguma microinteração (ex: barra montando, ícones de exercícios passando)
- Algoritmo cruza: dias/semana + duração + equipamentos + objetivo → gera divisão (A/B/C/D) com exercícios, séries, repetições e tempo de descanso

## 7. Paywall / Assinatura (ASAAS)
- Pode aparecer aqui (treino gerado como "prévia", desbloqueio completo mediante assinatura) ou logo após o cadastro, dependendo da estratégia de conversão
- Planos (mensal/anual), checkout via ASAAS (Pix, cartão, boleto)

## 8. Tela principal (Home)
- Treino do dia em destaque
- Progresso da semana (dias treinados x planejados)
- Atalho para histórico

## 9. Tela de treino do dia
- Lista de exercícios do dia com miniatura de imagem
- Ordem de execução, séries x repetições, carga sugerida/registrada

## 10. Tela de execução do exercício
- Desenho/ilustração mostrando a postura correta
- Descrição textual passo a passo de como executar
- Botão "Ver no YouTube" (abre busca ou vídeo específico do exercício)
- Campo para registrar carga usada e sensação (RPE) — alimenta o histórico

## 11. Histórico / Evolução
- Gráfico de carga por exercício ao longo do tempo
- Calendário de dias treinados

## 12. Configurações
- Editar dados pessoais e equipamentos disponíveis (permite regerar o treino)
- Gerenciar assinatura
