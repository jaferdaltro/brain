---
apple-notes-id: 62A2967A-C24E-4ECB-947F-29E5A8C76A56
---
### Executar irb carregando um código

```
bundle exec irb -r ./worker.rb

```
### Executa um worker especifico com Sidekiq

```
bundle exec sidekiq -r ./worker.rb
```