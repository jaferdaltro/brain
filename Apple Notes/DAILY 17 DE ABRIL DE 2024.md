---
apple-notes-id: 2F6E096F-D4B6-49B3-A45D-128D22E19FE8
---
### RE-5670 EDIT STATION - INSUFFICIENT QA CRITERIA
> https://github.pie.apple.com/reliability/recon-ui/pull/1941

> 1. Edited value is getting displayed on the left side even when user has not saved the edited details❌
> 3. User needs to refresh the page to see the edited station name in alphabetical order ❌

### RE-5669 CREATE NEW STATION - INSUFFICIENT QA CRITERIA
- Caracteres especiais✅

### RE-5674 - EXPORT RULES

project-config/station-editor/11/all


      this.route('station-editor', function () {
        this.route('station', { path: ':station_id' }, function () {
          this.route('build', { path: ':build_id' }, function () {
            this.route('export-rules');
          });
        });
      });




 <ul class="station-editor-tab nav nav-tabs">
    <li class="station-editor-tab__active-tab">
      <LinkTo @route='project-config.station-editor.station.build.export-rules'>EXPORT RULES</LinkTo>
    </li>
    <li class="station-editor-tab__disabled-tab"><a href="#">LIMITS <i class="fa fa-info-circle"></i></a></li>
    <li class="station-editor-tab__disabled-tab"><a href="#">FA TRACKER</a></li>
  </ul>
  {{outlet}}




- As tabs serão colocadas nesse endereço
	- app/templates/components/project-config/station-editor/station-column-tab.hbs
	- Dentro desse arquivo colocarei os componentes diretamente.
 



EXEMPLO DE LINKTO
  <LinkTo
    data-test-station-name={{@station.name}}
    @tagName="div"
    @classNames="station-editor__station"
    @activeClass="station-editor__station--active"
    @route="project-config.station-editor.station"
    @model={{@station.id}}
  >
    <div>
      <div
        data-test-station-name-field={{@station.id}}
        class="station-editor__station-name"
      >
        {{@station.name}} {{#if @station.stationAlias}} ({{@station.stationAlias}}) {{/if}}
      </div>
    </div>

    <div class="station-editor__station-actions">
      <div>
        <i
          class="fa fa-pencil"
          data-test-edit-button={{@station.id}}
          {{on "click" (stop-propagation (fn (mut this.editing) true))}}
        ></i>
        <EmberTooltip>Edit this station.</EmberTooltip>
      </div>

      {{#if (user-has-permission "engineer_admin")}}
        <div>
          <i
            class="fa fa-trash-o station-editor__delete"
            data-test-delete-button
            {{on "click" (stop-propagation (fn @deleteStation @station))}}
          ></i>
          <EmberTooltip>Delete this station.</EmberTooltip>
        </div>
      {{/if}}
    </div>
  </LinkTo>