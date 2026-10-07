---
apple-notes-id: BEEFC084-DA72-4711-936F-12A2042CE585
---
Car.all.each do |u|
  File.write('db/seeds.rb', "Car.create(vtr:'#{u.vtr}', licence_plate: '#{u.licence_plate}', owner: '#{u.owner}', brand: '#{u.brand}', model: '#{u.model}')\n", mode: "a")
 end