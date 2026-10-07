---
apple-notes-id: 2BB0C6D2-77D0-4DC6-A65F-FA403B462B11
---
- working on ticket 5670 to make suggest modifications  on station editor weekly

- Alterações 
	- Geral
		- no segundo campo (station alias), mudar o placeholder para "Station Alias (optional)"
		- quando o usuário editar APENAS o alias, remover o texto dizendo que pode dar problema (deixar só titulo e botões)
	- Edit Station


![[image 1.png]]



  <ProjectConfig::StationEditor::StationModal
    data-test-station-modal
    *@*label="Edit Station"
    *@*station={{@station}}
    *@*onSave={{fn (mut this.showConfirmationModal) true}}
    *@*onNameChange={{fn (mut this.nameChanged) true}}
    *@*handleInputChange={{this.handleInputChange}}
    *@*onCancel={{this.cancelEdit}}
  />