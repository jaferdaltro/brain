---
apple-notes-id: 51123EC8-C512-4063-AF4E-584B42E91877
---
```
app/routes/project-config/station-editor/station/build.js    

if (buildId === 'all') {
      stationColumns = await this.stationColumnService.loadStationColumns(stationId);
    } else if (teamId) {
      stationColumns = await this.stationColumnService.loadTeamStationColumnOverrides(stationId, buildId, teamId);
    } else {
      stationColumns = await this.stationColumnService.loadStationColumnOverrides(stationId, buildId);
    }
```




```
app/templates/project-config/station-editor/station/build.hbs

<ProjectConfig::StationEditor::StationColumnEditor
  @stationId={{@model.stationId}}
  @buildId={{@model.buildId}}
  @teamId={{this.teamId}}
  @stationColumns={{@model.stationColumns}}
  @changes={{this.changes}}
  @updateChanges={{this.updateChanges}}
  @reload={{route-action "reload"}}
/>
```



```
app/templates/components/project-config/station-editor/station-column-editor.hbs
```


```
app/templates/components/project-config/station-editor/station-column-editor/station-column-override-row.hbs
```