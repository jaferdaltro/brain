---
apple-notes-id: A4175162-1903-4BCA-80F3-16BFE962D42B
---
car index
<div class="table-responsive">
  <table class="table table-striped table-bordered table-hover">
      <thead>
          <tr>
              <th>#</th>
              <th> VTR</th>
              <th>PLACA</th>
              <th>
                <%= link_to new_car_path, class:"btn btn-success btn-circle" do %>
                  <i class="fa fa-plus"></i>
                <% end %>
              </th>
          </tr>
      </thead>
      <tbody>
          <% @cars.each do |car| %>
          <tr>
              <td><%= car.id %></td>
              <td><%=link_to car.vtr, car_path(car) %></td>
              <td><%= link_to car.licence_plate, car_path(car) %></td>
              <td style="width: 120px">
                <%= link_to edit_car_path(car), class:"btn btn-primary btn-circle" do %>
                  <i class="fa fa-edit fa-xs "></i>
                <% end %>

                <%= link_to car_path(car), method: :delete, 
                    class:"btn btn-danger btn-circle", 
                    data: { confirm: t('tem certeza?' ) }  do %>
                  <i class="fa fa-minus fa-xs"></i>
                <% end %>
              </td>
          </tr>
          <% end %>
      </tbody>
  </table>
</div>