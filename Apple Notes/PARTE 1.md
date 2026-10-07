---
apple-notes-id: C0A674C6-F878-4A20-B99C-9BD5047B9D6C
---
```
rails g model User name:string document:string kind:integer status:integer notes:text

rails g model Client name:string company_name:string document:string email:string phone:string user:references notes:text status:integer

rails g model Address country:string city:string state:string neighborhood:string street:string number:string client:references user_id:integer

rails g model Category name:string

rails g model Product name:string description:text status:integer category:references

rails g model Discount name:string description:text value:integer kind:integer status:integer

rails g model ProductQuantity product:references quantity:integer user:references

rails g model Order description:string product:references user:references client:references amount:float width:float height:float m2:float m2_charged:float taxes:decimal obs:text

rails g model Sale client:references sale_date:date user:references discount:references notes:text

rails g model Comission sale:references value:decimal user:references status:integer note:text



rails db:migrate

class User < ApplicationRecord
  enum kind: [:salesman, :manager]
  enum status: [:active, :inactive]
  has_many :comissions
  has_many :addresses
  has_many :clients
  has_many :product_quantities
  has_many :sales
end

class Client < ApplicationRecord
  belongs_to :user
  enum status: [:active, :inactive]
  has_one :address
end

class Address < ApplicationRecord
  belongs_to :client
end

class Product < ApplicationRecord
  enum status: [:active, :inactive]
  has_many :product_quantities
end

class Discount < ApplicationRecord
  enum status: [:active, :inactive]
end

class ProductQuantity < ApplicationRecord
  belongs_to :product
  belongs_to :sale, optional: true
end

class Sale < ApplicationRecord
  belongs_to :client
  belongs_to :user
  belongs_to :discount
  has_many :product_quantities
end

class Comission < ApplicationRecord
  belongs_to :sale
  belongs_to :user
end

gem 'rails_admin'

bundle
rails g rails_admin:install

Seed:
```
### # Criando nossos Users --- OBS: Depois que adicionarmos o devise precisamos incluir o email e senha dos users

```
User.create name: 'José', status: :active, kind: :salesman
User.create name: 'Marcos', status: :active, kind: :manager

```
### # Criando alguns produtos de exemplo

```
Product.create name: 'Smartphone', description:'Um smartphone novo ...', status: :active
Product.create name: 'Tablet', description:'Um tablet novo ...', status: :active

```
### # Criando um desconto de exemplo

```
Discount.create name: 'Desconto carnaval', description: 'Aplique esse desconto no carnaval', value: '10', kind: :porcent, status: :active

rake db:seed
```