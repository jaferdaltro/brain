---
apple-notes-id: 509E6E04-3BD4-4AD7-891E-186CBB3C9F7C
---
def close
	self.update_column(:canceled_at, Time.zone.now)
end

def close_open_carts(cart_ids)
	cart_ids.each do |cart_id|
		cart = Cart.where(id: cart_id).first
		cart.close
	end
end