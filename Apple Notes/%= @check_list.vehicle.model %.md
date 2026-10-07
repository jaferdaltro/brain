---
apple-notes-id: DF6E1D61-83B2-455E-86BB-EBF87B9525DC
---
<% @check_list.check_items.each *do* |check_item| %>
<%= link_to check_item.description, check_list_path %>


 <input *type*="text" *class*="form-control" *placeholder*="Km inicial" *aria-label*="Username" *aria-describedby*="basic-addon1">



bootstrap@5.0.0-beta3