
# 🔐 FUNCIONALIDADE 1 — Autenticação e Usuários (Base do Sistema)

> **Objetivo:** permitir que professores, pais, coordenação e direção façam login com segurança e tenham acesso apenas ao que lhes compete.

---

## 1️⃣ Decisões iniciais (antes de codar)

- **Backend**: Rails (monolítico para MVP)
    
- **Banco**: PostgreSQL
    
- **Autenticação**: Devise
    
- **Controle de acesso (roles)**: enum no User + Pundit depois
    

---

## 2️⃣ Criação do projeto no Replit

Checklist:

-  Criar Repl → Ruby on Rails
    
-  Configurar PostgreSQL
    
-  Rodar `rails db:create`
    

---

## 3️⃣ Model de Usuário

### Tipos de usuários (roles):

- `professor`    
- `pai`
- `coordenador`
- `diretor`
- `aluno`

### Campos mínimos do `User`:

- nome
    
- email
    
- password
    
- role
    
- ativo (boolean)
    

---

## 4️⃣ Implementar Login (Devise)

Checklist técnico:

-  Adicionar gem `devise`
    
-  `rails generate devise:install`
    
-  `rails generate devise User`
    
-  Migrar banco
    

📌 **Configuração importante**

- Login por e-mail
    
- Confirmação de senha
    
- Reset de senha
    

---

## 5️⃣ Controle de acesso básico (MVP)

No model `User`:

```ruby
enum role: {
  professor: 0,
  pai: 1,
  coordenador: 2,
  diretor: 3
}
```

Validações:

- presença de role
    
- e-mail único
    

---

## 6️⃣ Cadastro de usuários (MVP simples)

Regra importante desde já:

🚫 Pais **não se cadastram sozinhos**  
✅ Coordenação/Direção cria usuários

Funcionalidades:

- Tela de cadastro de usuário
    
- Definir role no momento da criação
    
- Ativar/desativar usuário
    

---

## 7️⃣ Redirecionamento após login

Após login, cada role vai para seu dashboard:

- Professor → `/professor/dashboard`
    
- Pai → `/pais/dashboard`
    
- Coordenação → `/coordenacao/dashboard`
    
- Direção → `/direcao/dashboard`
    

---

## 8️⃣ Proteção de rotas

Checklist:

-  `before_action :authenticate_user!`
    
-  Verificar role antes de acessar controllers
    
-  Usuário desativado não consegue logar
    

---

## 9️⃣ Teste manual no Replit

Cenário mínimo:

- Criar 1 usuário de cada role
    
- Testar login/logout
    
- Testar acesso indevido (pai tentando acessar área do professor)
    

---

## 🎯 Resultado dessa funcionalidade

Ao final você terá:

✅ Login funcionando  
✅ Usuários separados por perfil  
✅ Base segura para o resto do sistema  
✅ Estrutura pronta para escalar

---

## ▶️ Próximo passo

Quando você terminar essa parte, me diga e seguimos para a **FUNCIONALIDADE 2**, que eu sugiro:

➡️ **Cadastro de alunos, turmas e vínculo com pais e professores**

Se quiser, no próximo passo posso:

- Te passar **comandos exatos do Rails**
    
- Ou montar **a estrutura de pastas e controllers**
    
- Ou adaptar tudo para outro stack no Replit
    

👉 Me diga quando estiver pronto para a próxima funcionalidade.
