---
apple-notes-id: 93CD4FBC-E841-456B-80B0-9E8D090E7425
---
<div class="d-flex justify-content-between">
 
    <% if item.ready %>
      <span class='text-muted'>
        <%= item.description %>
      </span>
      <%= link_to ready_car_item_path(item), method: :patch, class:'btn btn-info'  do %>
          <i class='fas fa-check'></i>
      <% end %>
    <% else %>
      <span class='text-muted'>
        <%= item.description %>
      </span>
      <%= link_to unready_car_item_path(item), method: :patch, class:'btn btn-dark'  do %>
          <i class='fas fa-times'></i>
      <% end %>
    <% end %>
  </div>
</li>