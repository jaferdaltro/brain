---
apple-notes-id: 4549FEE7-40B3-46DE-AD9A-AEF2B2EF2A4F
---
#terminal #sandbox #ruby 

### Debugging Live Process

```
    bundle exec rdbg -O -n -c -- bin/rails server -p 3000
```


```
    def self.find_or_create_for(tenant)
      event = find_by(status: nil, tenant: tenant) || create_for(tenant)
      if tenant && tenant.phc_events.where(order_identifier: event.order_identifier).count > 1
        event.update!(status: statuses.keys[0])
        return Billing::PhcEvent.find_or_create_for(tenant)
      end
      event
    end
```

Pelo menos no ActiveRecord o uso de ! em uma clausula save(save!) 
- To raise an exception and see more details about the error - RecordInvalid
- RecordInvalid is raised when a record cannot be saved to the database due to a failed validation
Quando não usamos o bang(!) no save temos apenas um retorno boolean


```
class User < ApplicationRecord
  validates :username, presence: true, uniqueness: true
  validates :password, length: { minimum: 8 }
end

user = User.create!(username: nil, password: "Welcome")
# => ActiveRecord::RecordInvalid (Validation failed: Username can't be blank, Password is too short (minimum is 8 characters))

#Accesses an array of error messages from the `errors` object.
user.errors.full_messages
# => ["Username can't be blank", "Password is too short (minimum is 8 characters)"] 

#Accesses an array of error messages from the `errors` object.
user.errors.full_messages

```


```
def create
  begin
    user = User.create!(user_params)
    session[:user_id] = user.id
    render json: user, status: :created
  rescue ActiveRecord::RecordInvalid => exception
    render json: {errors: 
    exception.record.errors.full_messages}, status: 
    :unprocessable_entity
  end
end

```

### Colocar o rescue no Controller é uma excelente ideia

```
class ApplicationController < ActionController::API
   #rescue_from takes an exception class, and an exception 
   #handler method
   rescue_from ActiveRecord::RecordInvalid, with: 
   :unprocessable_entity_response

   private

   def unprocessable_entity_response(exception)
     render json: {errors: 
     exception.record.errors.full_messages}, status: 
     :unprocessable_entity
   end
end
```



### ActiveRecord exceptions 
[rails/activerecord/lib/active_record/errors.rb at main · rails/rails](https://github.com/rails/rails/blob/main/activerecord/lib/active_record/errors.rb)

[main.rb - AwfulSphericalIntelligence - Replit](https://replit.com/@jaferdaltro/AwfulSphericalIntelligence#main.rb) \#sandbox

[Exception Handling and Validations in Rails, and how to display errors to users. - DEV Community](https://dev.to/jaguilar89/exception-handling-and-validations-in-rails-and-how-to-display-errors-to-users-505l) 

### Para usar comandos fora do ruby rodando o irb

```
%x(ls)
```

### Mostra as task que tem dev

```
rails -T dev
```

### Error Handling 

![[IMG_5262.jpeg]]


[Class: Exception (Ruby 2.5.1)](https://ruby-doc.org/core-2.5.1/Exception.html)