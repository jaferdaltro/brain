---
apple-notes-id: 8EB64DCA-061B-4324-9CA2-BBDD8D35186F
---
<%= f.association :car, label_method: :vtr %>
  <%= car.items.each do |item| %>
    <%= item.description %>
  <% end %>
  <%= f.button :submit %>
<% end %>