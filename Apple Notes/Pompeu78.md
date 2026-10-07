---
apple-notes-id: AE619BC6-82FE-4C1C-9CB6-6C74F23DBCCB
---
const setupHelpScout = () => {
  const centerHelp = $('#open-help-center')
  const frequentAsks = $('#open-faq')
  const callSupport = $('#open-call-support')

  $(centerHelp).click( () => {
    window.Beacon('open')
    window.Beacon('navigate', '/docs/search?query=Como integrar com PJ Bank')
  })

  $(frequentAsks).click( () => {
    window.Beacon('open')
    window.Beacon('navigate', '/answers/')
  })

  $(callSupport).click( () => {
    window.Beacon('open')
    window.Beacon('navigate', '/ask/message')
  })
}

$(document).on('turbolinks:load', setupHelpScout)