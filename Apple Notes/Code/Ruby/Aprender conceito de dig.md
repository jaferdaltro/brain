---
apple-notes-id: 7C839E24-A4F1-4581-8AFD-EC87B39C2E3D
---
```

  def cancel_charging_link_for(invoice)
    return "" unless invoice.has_cobrato_charge?
    return "" unless invoice.can_cancel?
    return "" unless invoice.charging_with_banking_services?
    return "" if invoice.receivables.count > 1

    actions = link_actions.dig(
      :cancel_charging, invoice.payment_information.payment_method.to_sym
    )

    label_text, confirm = [actions[:cancel_label], actions[:cancel_confirm]]

    conditional_link_structure_for(
      invoice, :cancel_charging,
      label: "#{fa_icon(actions.dig(:button_icon))} #{label_text}".html_safe,
      confirm: confirm
    )
  end
```

ActiveRecord::Relation

```
subject.collect(&:movie)
subject.collect.pluck(:movie)
```