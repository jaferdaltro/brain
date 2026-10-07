---
apple-notes-id: 62460462-47A4-437A-BAA9-210EBD3489AA
---
# I18n config
    config.i18n.load_path += Dir\[Rails.root.join('config/locales/**/*.{rb,yml}')\]
    config.i18n.default_locale = :'pt-BR'

rails_helper.rb spec
Dir\[Rails.root.join('spec', 'support', '**', '*.rb')\].each { |f| require f }