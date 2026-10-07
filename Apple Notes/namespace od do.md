---
apple-notes-id: 9F085392-8E9F-4417-AA4D-ACD63AF8A139
---
post '/oauth/token' to: 'authorization#token'
      namespace :v1 do
        
      end
    end

Migration - open delivery
class AddOpenDeliveryColumnsToIntegrations < ActiveRecord::Migration\[6.1\]
  def change
    add_column :integrations, :open_delivery_client_id, :string
    add_column :integrations, :open_delivery_client_secret, :string
  end
end