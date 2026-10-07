---
apple-notes-id: 01B1BA07-5174-42D4-A1B9-D88A51064FBE
---
def change
    create_table :albums_players, id: false do |t|
      t.belongs_to :album
      t.belongs_to :player
    end
  end
end

<h1>Albums</h1>

<table>
  <thead>
     <tr>
      <th>Abum</th>
      <th>Player</th>
      <th colspan="3"></th>
    </tr>
  </thead>

  <tbody>
    <% @albums.each do |album| %>
      <tr>
        <td><%= album.name %></td>
          
        <td><%= album.player.name %></td>
      </tr>
    <% end %>
  </tbody>
</table>