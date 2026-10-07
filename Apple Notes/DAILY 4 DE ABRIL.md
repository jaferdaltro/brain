---
apple-notes-id: 6C91B31A-CBD1-4D38-BDC2-C044B02E68E4
---
- Refatorado atividades RE-5670 E RE-5669

Waiver Rules

DEV_APPLECONNECT_EMAIL=johnny_appleseed@apple.com bundle exec sidekiq
DEV_APPLECONNECT_EMAIL=johnny_appleseed@apple.com berails s
ember server --proxy http://localhost:3000

- Concluída as alterações solicitadas na weekly do Station Editor para o [RE-5670](https://github.pie.apple.com/reliability/recon-ui/pull/1927) e [RE-5669](https://github.pie.apple.com/reliability/recon-ui/pull/1931)
- Sync com Ariel para mostrar as alterações realizadas dos tickets mencionados acima e confirmações sobre o ticket [RE-5672](https://compass.scv.apple.com/jira/browse/RE-5672)
- Sync com o Cunha para resolver conflitos nos PRs
- Avaliação do inicio da atividade do ticket [RE-5672](https://compass.scv.apple.com/jira/browse/RE-5672)


### STANDUP
- RESOLVED SOME CONFLICTS IN 5670
- CONCLUDED THE CHANGES IN **5670(OPENED PR)** AND 5669 REQUIRED TO STATION EDITOR WEEKLY 
- WORKING ON TICKET RE-5672

### PR - REVIEW

- ABERTO O PR PARA O RE-5670 PEDIR O REVIEW NA STANDUP FOR TIFF

  <div class="station-editor__content content-block content-block--with-shadow">
	{{outlet}}
	<dir>
	  <h1>test</h1>
	</dir>
  </div>