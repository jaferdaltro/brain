---
apple-notes-id: 7D2FDFEA-4DE7-49AD-AAFA-015ADA0C5ACB
---
<ul class="navbar-nav mr-auto">
    

      <% if current_user.admin? %>
       <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
               Configuração de Viaturas
            </a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                <%= link_to "Nova Viatura", new_car_path, class:"dropdown-item"  %>
            </div>
        </li>
      <% end %>
      <li class="nav navbar-nav navbar-right">
        <%= link_to 'Viaturas', cars_path, class:"nav-link" %>
      </li>
   
    </ul>
      <% if logged_in? %>
        <li class="nav navbar-nav navbar-right">
          <%= link_to 'sair', logout_path, method: :delete, data: {confirm: 'Tem certeza ?'}, class:"nav-link" %>
        </li>
      <% end %>
      
  </div>