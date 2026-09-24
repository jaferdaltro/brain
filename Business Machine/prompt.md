Perfeito 👍  
Rails 8 + Hotwire + Hotwire Native é **uma escolha excelente** para esse tipo de sistema (MVP rápido, menos JS, app web + mobile).

Vou dividir em **passos funcionais**, bem objetivos, começando **exclusivamente pela autenticação e usuários**.  
Todas as **entidades estarão em inglês**, como você pediu.

---

# 🔹 STEP 1 — Authentication & Users

## 🎯 Objetivo do passo

Permitir que **teachers, parents, coordinators e principals** façam login no sistema, com **papéis (roles)** bem definidos e prontos para autorização futura.

---

## 1. Entidade principal

### `User`

Campos sugeridos:

```ruby
User
- id
- name:string
- email:string
- password_digest:string
- role:integer
- active:boolean (default: true)
- created_at
- updated_at
```

### Roles (enum)

```ruby
enum role: {
  teacher: 0,
  parent: 1,
  coordinator: 2,
  principal: 3
}
```

👉 Isso facilita autorização depois com Pundit/Policies.

---

## 2. Autenticação

### Escolha recomendada

✅ **Devise** (totalmente compatível com Hotwire)

Funcionalidades iniciais:

- Login
    
- Logout
    
- Password reset
    
- Remember me (opcional)
    

Hotwire funciona bem com:

- Turbo Frames para formulários
    
- Turbo Streams para feedback de erro
    

---

## 3. Telas (Views)

### 📄 Login

- Email
    
- Password
    
- Botão “Login”
    

Hotwire:

- Form com `data-turbo="true"`
    
- Erros renderizados sem reload completo
    

---

### 📄 Forgot Password

- Campo email
    
- Envio de instruções
    

---

### 📄 First Access (opcional, mas recomendado)

Para escolas:

- Usuário criado pelo admin
    
- Professor/pai define senha no primeiro acesso
    

---

## 4. Fluxo de autenticação

1. Usuário acessa `/login`
    
2. Autenticação via Devise
    
3. Após login:
    
    - Redirecionamento por `role`
        
        - teacher → `/teacher/dashboard`
            
        - parent → `/parent/dashboard`
            
        - coordinator → `/coordinator/dashboard`
            
        - principal → `/principal/dashboard`
            

---

## 5. Controllers

### `Users::SessionsController`

- Override do Devise (se necessário)
    
- Redirecionamento por role
    

### `ApplicationController`

```ruby
before_action :authenticate_user!
```

---

## 6. Autorização (base para próximos passos)

Mesmo que você implemente depois, já prepare:

- **Pundit**
    
- Policies por role
    
- Exemplo futuro:
    
    - `MessagePolicy`
        
    - `EventPolicy`
        

---

## 7. Seeds (para desenvolvimento)

Criar usuários básicos:

- 1 teacher
    
- 1 parent
    
- 1 coordinator
    
- 1 principal
    

Isso acelera muito os próximos passos.

---

## 8. Hotwire Native (preparação)

Mesmo nesse passo inicial:

- Layout simples e responsivo
    
- Evitar JS customizado
    
- Forms e links compatíveis com Turbo
    

---

## ✔️ Checklist do STEP 1

-  User model com roles
    
-  Devise configurado
    
-  Login / Logout funcionando
    
-  Redirecionamento por role
    
-  Base de autorização pronta
    
-  Seeds criados
    

---

Quando você concluir esse passo, **me diga qual funcionalidade quer seguir**, por exemplo:

- 📩 Messaging (Teacher ↔ Parent)
    
- 📚 Classroom Content
    
- 🗓️ Events & Exams
    
- 👨‍🎓 Students & Classes
    

Aí eu continuo do **STEP 2 em diante**, sempre nesse nível de detalhamento.