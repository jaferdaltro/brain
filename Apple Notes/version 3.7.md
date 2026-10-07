---
apple-notes-id: 50C2825A-00E0-484E-93E7-78F186C6F54B
---
services:
  db:
    image: postgres:9.6.20-alpine
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