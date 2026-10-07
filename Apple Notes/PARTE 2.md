---
apple-notes-id: 60A46F3C-7C6B-4F0B-9561-ABE05AEF6BFE
---
```
# Gemfile

gem 'devise'

rails generate devise:install

rails generate devise User

```
### # /config/initializers/rails_admin.rb

```

## == Devise ==
config.authenticate_with do
  warden.authenticate! scope: :user
end
config.current_user_method(&:current_user)

```
### # /db/seeds.rb

```

User.create name: 'José', status: :active, kind: :salesman, email: 'salesman@teste.com', password: 123456
User.create name: 'Manuel', status: :active, kind: :salesman, email: 'salesman2@teste.com', password: 123456
User.create name: 'Marcos', status: :active, kind: :manager, email: 'manager@teste.com', password: 123456

```
### # Criando alguns produtos de exemplo

```
Product.create name: 'Smartphone', description:'Um smartphone novo ...', status: :active
Product.create name: 'Tablet', description:'Um tablet novo ...', status: :active

```
### # Criando um desconto de exemplo

```
Discount.create name: 'Desconto carnaval', description: 'Aplique esse desconto no carnaval', value: '10', kind: :porcent, status: :active

rake db:drop

rake db:create

rake db:migrate

rake db:seed

```
### # Gemfile

```

gem 'cancancan', '~> 1.15.0'

rails g cancan:ability

```
### # /config/initializers/rails_admin.rb

```

## == Cancan ==
config.authorize_with :cancan

```
### # app/models/ability.rb

```

class Ability
  include CanCan::Ability
 
  def initialize(user)
    if user
      if user.kind == 'salesman'
        can :access, :rails_admin
        can :read, :dashboard
        can :manage, Client, user_id: user.id
        can :manage, Sale, user_id: user.id
        can :read, Product, status: :active
        can :read, Discount, status: :active
        can :read, Comission, user_id: user.id
        can :manage, ProductQuantity, user_id: user.id
        can :manage, Address, user_id: user.id
      elsif user.kind == 'manager'
        can :manage, :all
      end
    end
  end
end
```