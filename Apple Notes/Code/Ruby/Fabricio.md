---
apple-notes-id: 8156F4C3-A8A1-47EC-85A8-BA1708DF6E79
---
<p style="text-align:right;margin:0">
</p>
git push origin BIL-README --force
git reset --mixed 01617de17fd4c37ab106d86aeeccad28953f65f7

git commit -a --amend

version: "3.7"
services:
  db:
    image: postgres:9.6.20-alpine
    ports:
	  - 5433:5433
    environment:
      POSTGRES_DB: pscontracts_development
      POSTGRES_PASSWORD: pgpass
    volumes:
	  - ./.data:/var/lib/postgresql/data
  redis:
    image: "redis:4.0.14-alpine"
    command: redis-server
    ports:
	 - 6380:6380

D