# CLAUDE.md

Este arquivo orienta o Claude (via Claude Code) ao trabalhar neste repositório.

## Visão geral do projeto

App mobile de montagem de treino de musculação personalizado. O usuário informa dados pessoais,
disponibilidade de dias/tempo e os equipamentos que tem acesso (selecionados visualmente por
imagem, não por texto), e o app gera um treino sob medida. Cada exercício é exibido com
ilustração, descrição textual de execução e link para vídeo no YouTube.

## Stack tecnológica

- **Framework**: React Native + TypeScript
- **Plataformas**: iOS e Android (build único, sem código nativo customizado salvo necessidade)
- **Pagamento/assinatura**: ASAAS (Pix, cartão, boleto)
- **Navegação**: React Navigation (stack + tabs)
- **Gerenciamento de estado**: a definir (Zustand ou Context API recomendado para escopo do app)
- **Persistência local**: AsyncStorage ou similar para dados offline-first

## Estrutura de pastas sugerida

```
src/
  screens/
    onboarding/
    workout/
    exercise/
    history/
    settings/
    paywall/
  components/
    EquipmentGrid/
    ExerciseCard/
    Stepper/
  navigation/
  services/
    asaas/
    workoutGenerator/
  types/
  assets/
    equipment/       # imagens dos equipamentos
    exercises/        # ilustrações dos exercícios
```

## Funcionalidades principais

1. **Seleção de equipamentos** — grid visual (imagem, não texto), múltipla seleção
2. **Coleta de dados do usuário** — peso, altura, idade, sexo (stepper, uma pergunta por tela)
3. **Preferências de treino** — dias por semana, duração da sessão
4. **Geração de treino** — algoritmo que cruza equipamentos + disponibilidade + dados do usuário
5. **Execução do exercício** — ilustração + texto explicativo + botão para vídeo no YouTube
6. **Assinatura via ASAAS** — checkout e gestão de plano

## Convenções de código

- Componentes funcionais + hooks
- Tipagem estrita (evitar `any`)
- Um componente por arquivo, nome do arquivo = nome do componente
- Estilos com StyleSheet.create (ou styled-components, definir antes de escalar)

## Design / UX

- Interface moderna, poucos textos por tela (uma decisão por vez)
- Seleção de equipamentos deve ser tátil e visual (cards de imagem, feedback claro de seleção)
- Fluxo de onboarding curto — cada fricção a mais reduz conversão

## Comandos de desenvolvimento

```
npm install
npx react-native run-ios
npx react-native run-android
```

(Ajustar conforme setup final do projeto — Expo ou React Native CLI puro, a decidir.)

## Notas sobre integração ASAAS

- Chaves de API nunca devem ficar hardcoded no app — usar backend intermediário para gerar
  cobranças e validar webhooks de pagamento
- Fluxo recomendado: app → backend próprio → API ASAAS → webhook de confirmação → libera acesso


mw_kUWwyrc7XU_vnylqHMLUjNhvSm15lkAV7d9gdTQqzDk