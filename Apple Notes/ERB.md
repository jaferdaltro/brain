---
apple-notes-id: 399F2CEB-5118-4E9F-B74C-016F625F0C51
---
#erb #crab #ruby #vscode #shortcut 

### Simple Ruby ERB

Command erb.toggleTags
Supports multiple line/selection. Cycles through the tags <%= %>, <% %> and <%# %>.

// Your keyboard shortcuts
{
  "key": "ctrl+shift+`",
  "command": "erb.toggleTags",
  "when": "editorTextFocus && editorLangId == erb"
},




Depois de instalar a extensão no VSCode, adicione ao projeto a **gem "htmlbeautifier" no ambiente de desenvolvimento** e execute o bundle
Manage > Settings ... > Clique no ícone da **peça de quebra cabeça** no lado superior esquerdo com a descrição **"Open Settings (JSON)"**, e adicione
"\[erb\]": {
  "editor.defaultFormatter": "aliariff.vscode-erb-beautify",
  "editor.formatOnSave": true
},
"files.associations": {
  "*.html.erb": "erb"
},
**"emmet.includeLanguages": {**
**"erb": "html"**
**}**

Abra um arquivo da pasta view com html.erb e verifique se está **auto-completando**, por exemplo colocando:
**p + \[TAB ou Enter\]** = <p></p>
**div + \[TAB ou Enter\]** = <div></div>

**.nomedaclasse + \[TAB ou Enter\]** = <div class="nomedaclasse"></div>