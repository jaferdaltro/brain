---
apple-notes-id: 897BCE6E-099A-44DD-B0E9-9EF6F5F81B60
---
<div class='card'>
    <div class="card-header d-flex justify-content-between">
      <select name="vehicle_id">
        <%= @cars.each do |car| %>
          <option value="<%= car.id %>">VTR-<%= car.licence_plate  %></option>
        <% end %>
      </select>
    </div>

  <div class="card-body">
      <%= form_with(model: car, local: true) do |f| %>
        <div class="input-group mb-4">
          <%= f.number_field :beggin_km, class: 'form-control', placeholder: 'Quilometragem inicial' %>
          <%= f.number_field :end_km, class: 'form-control', placeholder: 'Quilometragem final' %>
        </div>
        <ul class='list-group'>
          <% @check_list.items.each do |item| %>
            
              <li class='list-group-item bg-light'>
                <div class='d-flex justify-content-between'>
                  <span class='text-muted'>
                      <%= item.description.upcase! %>
                  </span>
                  <div class="row">
                    <%= link_to '#', class: 'btn btn-success' do%>
                      <i class='fas fa-times'></i>
                    <% end %>
                    
                  </div>
                </div> 
              </li>  
           
             
                  
             
       
          <% end %>
    </ul> 
    <div class="input-group-append">
        <%= f.submit "OK", class: 'btn btn-primary input-group-btn' %>
      </div>
      <% end %>

  
     
  </div>
</div>