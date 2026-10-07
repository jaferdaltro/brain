---
apple-notes-id: D5F40C3C-D9BA-4F9B-BF60-C61F313B58BA
---
<div class="container" id='nav'>
    <%= link_to "sample app", user_path(current_user), id: "logo" %>
    <nav>
      <ul class="nav navbar-nav navbar-right">
        <li><%= link_to "Home", user_path(current_user) %></li>
        <% if current_user.admin? %>
          <li class="dropdown">
            <a href="#" class="dropdown-toggle" data-toggle="dropdown">
              Account <b class="caret"></b>
            </a>
            <ul class="dropdown-menu">
              <li><%= link_to "Profile", current_user %></li>
              <li><%= link_to "Settings", '#' %></li>
              <li class="divider"></li>
            </ul>
          </li>
        <% end %>
        <%= link_to 'sair', logout_path, method: :delete, 
          data: {confirm: 'Tem certeza ?'}, class:"nav-link" %>
      </ul>
    </nav>
  </div>
</header>