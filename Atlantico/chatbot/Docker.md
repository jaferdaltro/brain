
### Docker Essential Commands

```
# List local images
docker images

# Pull an image from Docker Hub
docker pull nginx

# Build an image from a local Dockerfile
docker build -t my-app .

# Start a container in detached mode
docker run -d -p 8080:80 --name web nginx

# View container logs
docker logs web

# Stop and remove a container
docker stop web && docker rm web

# Access contaier bash
docker exec -it web
```

```
"127.0.0.1:8081:80" # HOST_IP:HOST_PORT:CONTAINER_PORT
```
