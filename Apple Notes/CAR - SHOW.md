---
apple-notes-id: 7FB7E84D-803C-4141-88B0-9A273C5E08C0
---
<%= provide(:title, @car.vtr) %>

<div class="card-header d-flex justify-content-between">
  <div>
  <h5><b> Viatura <%= @car.vtr %> </b></h5>
  </div>
</div>

<div class='card-body'> 
  <ul class="list-group">

    <li class="list-group-item bg-light">
      <div class="d-flex justify-content-between">
        <span class='text-muted'>
          Placa
        </span>
        <span>
          <%= @car.licence_plate %>
        </span>
      </div>
    </li>
    <li class="list-group-item bg-light">
      <div class="d-flex justify-content-between">
        <span class='text-muted'>
          Proprietário
        </span>
        <span>
          <%= @car.owner %>
        </span>
      </div>
    </li>
    <li class="list-group-item bg-light">
      <div class="d-flex justify-content-between">
        <span class='text-muted'>
          Marca:
        </span>
        <span>
          <%= @car.brand %>
        </span>
      </div>
    </li>
    <li class="list-group-item bg-light">
      <div class="d-flex justify-content-between">
        <span class='text-muted'>
          Modelo:
        </span>
        <span>
          <%= @car.model %>
        </span>
      </div>
    </li>
    <% @car.items.each do |item| %>
      <%= render 'items/item', item: item %>
    <% end %>
  </ul>
</div>