---
apple-notes-id: DF26162E-F199-48FF-AD87-FDABBDE30A82
---
### app/model/sale.rb

```
has_one :comission


```
### # Adicionar no arquivo:
### /app/models/discount.rb


```
has_many :sales


```
### # **Alterar a linha “has_one: address” em “/app/models/client.rb” por:**

```
has_many :address

rails g migration add_sale_id_to_product_quantity sale_id:integer

rails g migration add_price_to_product price:decimal

rake db:migrate

enum status: [:pending, :payd]

```
### # Criando nossos Users --- OBS: Depois que adicionarmos o devise precisamos incluir o email e senha dos users

```
User.create name: 'José', status: :active, kind: :salesman, email: 'salesman@teste.com', password: 123456
User.create name: 'Manuel', status: :active, kind: :salesman, email: 'salesman2@teste.com', password: 123456
User.create name: 'Marcos', status: :active, kind: :manager, email: 'manager@teste.com', password: 123456

```
### # Criando alguns produtos de exemplo

```
Product.create name: 'Smartphone', description:'Um smartphone novo ...', status: :active, price: 10
Product.create name: 'Tablet', description:'Um tablet novo ...', status: :active, price: 20

```
### # Criando um desconto de exemplo

```
Discount.create name: 'Desconto carnaval', description: 'Aplique esse desconto no carnaval', value: '10', kind: :porcent, status: :active
Discount.create name: 'Desconto carnaval dinheiro', description: 'Aplique esse desconto quando possível', value: '10', kind: :money, status: :active

```
### # Crindo client

```
Client.create name: 'Paulo', company_name: 'Google', document: '1234', email: 'paulo@google.com', user: User.first
Client.create name: 'Julia', company_name: 'Google', document: 'abcd', email: 'julia@google.com', user: User.first

rake db:drop db:create db:migrate db:seed


```
### # **Adicionar no arquivo: /app/models/sale.rb**

```
after_save do
    calc = 0
    # Soma o preço dos produtos vezes a quantidade deles
    self.product_quantities.each {|p| calc += p.product.price * p.quantity}
    # Verifica se existe um desconto e aplica caso exista
    if self.discount
      if self.discount.kind == "porcent"
        calc -= calc / self.discount.value
      elsif self.discount.kind == "money"
        calc -= self.discount.value
      end
    end

    # Verifica se já existe uma comissão, caso sim atualiza, caso não cria uma nova.
    if self.comission.present?
      self.comission.update(value: (calc * 0.1), status: :pending)
    else
      Comission.create(value: (calc * 0.1), user: self.user, sale: self, status: :pending)
    end
  end
  
  config.model Sale do
  create do
    field  :client
    field  :sale_date
    field  :discount
    field  :notes
    field  :product_quantities

    field :user_id, :hidden do
      default_value do
        bindings[:view]._current_user.id
      end
    end
  end

  edit do
    field  :client
    field  :sale_date
    field  :discount
    field  :notes
    field  :product_quantities

    field :user_id, :hidden do
      default_value do
        bindings[:view]._current_user.id
      end
    end
  end
end

config.model Client do
  create do
    field  :name
    field  :company_name
    field  :document
    field  :email
    field  :phone
    field  :notes
    field  :status
    field  :address

    field :user_id, :hidden do
      default_value do
        bindings[:view]._current_user.id
      end
    end
  end

  edit do
    field  :name
    field  :company_name
    field  :document
    field  :email
    field  :phone
    field  :notes
    field  :status
    field  :address


    field :user_id, :hidden do
      default_value do
        bindings[:view]._current_user.id
      end
    end
  end

  list do
    field  :name
    field  :company_name
    field  :document
    field  :email
    field  :phone
    field  :notes
    field  :status
    field  :address

  end
end

config.model ProductQuantity do
  visible false
end

config.model Address do
  visible false
end


config.model ProductQuantity do
  edit do
    field :product
    field :quantity

    field :user_id, :hidden do
      default_value do
        bindings[:view]._current_user.id
      end
    end
  end
end

gem 'carrierwave'

bundle

rails generate uploader Photo

rails g migration add_photo_to_product photo:string

rake db:migrate

mount_uploader :photo, PhotoUploader
```