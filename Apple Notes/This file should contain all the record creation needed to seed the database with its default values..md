---
apple-notes-id: ED9DE89C-0743-4E60-AB14-5B3E5D269D94
---
*# The data can then be loaded with the rails db:seed command (or created alongside the database with db:setup).*
*#*
*# Examples:*
*#*
*#   movies = Movie.create(\[{ name: 'Star Wars' }, { name: 'Lord of the Rings' }\])*
*#   Character.create(name: 'Luke', movie: movies.first)*
*# vendors: okna persianas; donatelli- Alameda Gabriel Monteiro da Silva, 2113; persianas new york;*
*# Papel de Parede, Cortina, Cabeceira, Revestimento*

*\#USUARIOS*

```
User.create name: 'José', status: :active, kind: :salesman
User.create name: 'Marcos', status: :active, kind: :manager
```

*\#FORNECEDOR*
Vendor.create(description:'Casatto',contact_person:'Andrea', phone:'85-3278-1086', address:'Shopping Salinas', cnpj:'79437997979')
Vendor.create(description:'Okna Persianas',contact_person:'Okna', phone:'85-23234444', address:'Av.Santos Dummont, 343', cnpj:'79437997979')
Vendor.create(description:'Donatelli',contact_person:'Dona', phone:'85-23234444', address:'Alameda Gabriel Monteiro da Silva, 2113', cnpj:'79437997979')
Vendor.create(description:'Persianas New York',contact_person:'York', phone:'85-23234444', address:'Av.Santos Dummont, 777', cnpj:'79437997979')

*\#CATEGORIAS*
Category.create(description:'Papel de Parede')
Category.create(description:'Cortina')
Category.create(description:'Cabeceira')
Category.create(description:'Revestimento')

*\#PRODUTO - PAPEL DE PAREDE*
Product.create(description:'Clássicos', vendor_id:1, category_id: 1)
Product.create(description:'Temáticos', vendor_id:1, category_id: 1)
Product.create(description:'Contemporâneo', vendor_id:1, category_id: 1)
Product.create(description:'Listrados', vendor_id:1, category_id: 1)
Product.create(description:'Elementos Naturais', vendor_id:1, category_id: 1)
Product.create(description:'Florais', vendor_id:1, category_id: 1)
Product.create(description:'Lisos', vendor_id:1, category_id: 1)
Product.create(description:'Texturas', vendor_id:1 ,category_id: 1 )

*\#PRODUTO - CORTINA*
Product.create(description:'Tecidos', vendor_id:3 ,category_id: 2 )
Product.create(description:'Lumina', vendor_id:2 ,category_id: 2 )
Product.create(description:'Celular', vendor_id:2 ,category_id: 2 )
Product.create(description:'Plissada', vendor_id:2 ,category_id: 2 )

*\#PRODUTO - REVESTIMENTO*
Product.create(description:'Plissada', vendor_id:3 ,category_id: 4 )
Product.create(description:'Plissada', vendor_id:3 ,category_id: 4 )
Product.create(description:'Plissada', vendor_id:3 ,category_id: 4 )
Product.create(description:'Plissada', vendor_id:3 ,category_id: 4 )

*# CLIENTES*
Client.create name: 'Paulo', cpf_cnpj: '1234', email: 'paulo@google.com'
Client.create name: 'Julia', cpf_cnpj: 'abcd', email: 'julia@google.com'