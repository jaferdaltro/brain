---
apple-notes-id: 93D833DA-CC59-4302-A147-659270302F81
---
```
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV['RAILS_MAX_THREADS'] || 5 %>
  url: <%= ENV['DATABASE_URL'] %>

development: &development
  <<: *default
  database: pscontracts_development
  username: postgres
  password: pgpass
  host: 127.0.0.1
  port: 5434

test:
  <<: *default
  database: pscontracts_test<%= ENV['TEST_ENV_NUMBER'] %>
  username: postgres
  password: pgpass
  host: 127.0.0.1
  port: 5434

  profile:
    <<: *development

sandbox:
  <<: *default

production:
  <<: *default

```

docker-compose.yml

```
version: "3.7"
services:
  db:
    image: postgres:13-alpine
    ports:
      - 5434:5432
    environment:
      POSTGRES_DB: pscontracts_development
      POSTGRES_PASSWORD: pgpass
    volumes:
      - ./.data:/var/lib/postgresql/data
  redis:
    image: "redis:4.0.14-alpine"
    command: redis-server
    ports:
     - 6381:6379

```