---
apple-notes-id: 6F148A72-9276-41D6-8CC8-CA056E8F89B6
---
**gem 'shoulda-matchers', '~> 5.1'**
**gem 'factory_bot_rails', '~> 6.2'**


namespace :dev do
  desc "Setup development database"
  task setup: :environment do

    kinds = %w(Amigo Comercial Conhecido)
    kinds.each do |k|
      Kind.create(description: k )
    end
    puts "kinds sucessufuly created"

    puts "stat to create contacts"
    100.times do |i|
      Contact.create!(
        name: Faker::Name.name,
        email: Faker::Internet.email,
        birthdate: Faker::Date.between(65.years.ago, 18.years.ago),
        kind: Kind.all.sample
      )
    end
    puts "contact sucessifuly created"

    puts "creating phones"
    Contact.all.each do |contact|
      Random.rand(5).times do |i|
        contact.phones.create!(number: Faker::PhoneNumber.cell_phone) 
      end
    end
    puts "phones inserted in contacts"
  end
end