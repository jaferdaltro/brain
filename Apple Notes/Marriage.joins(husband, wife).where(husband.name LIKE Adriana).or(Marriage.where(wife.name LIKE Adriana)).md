---
apple-notes-id: 3CBA1766-BB39-4D5A-8339-F5EA46357567
---
```
    def index
      marriages = if params[:name].present?
        ::Marriage.by_name(params[:name]).includes(:husband, :wife, :address)
      else
        ::Marriage.includes(:husband, :wife, :address).order("users.name ASC")
        .page(current_page)
        .per(per_page)
      end

      render json: marriages,
             meta: meta_attributes(marriages),
             only: %i[id registered_by dinner_participation reason
                       children_quantity days_availability is_member
                       campus religion active],
             include: {
               husband: { only: %i[name phone email birth_at cpf role] },
               wife: { only: %i[name phone email birth_at cpf role] },
               address: { only: %i[street number neighborhood city state cep] }
             },
             root: true,
             status: :ok
    end
```