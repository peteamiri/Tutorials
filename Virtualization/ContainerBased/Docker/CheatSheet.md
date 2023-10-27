
The followings are the DOcket CLI cheatsheet


#### Basic Docker Commands:
- Build an image from a Dockerfile: `docker build -t <image_name> ...`
- Run a container from an image: `docker run <image_name>`- List running containers: `docker ps`- Stop a running container: `docker stop <container_id>`- Remove a container: `docker rm <container_id>`- List images: `docker images`
- Remove an image: `docker rmi <image_id>`

#### Container Management:
- Start a stopped container: `docker start <container_id>`- Attach to a running container: `docker attach <container_id>`- Execute a command in a running container: `docker exec <container_id> <command>`- Pause a running container: `docker pause <container_id>`
- Unpause a paused container: `docker unpause <container_id>`
- Restart a container: `docker restart <container_id>`

#### Networking:
- List networks: `docker network ls`- Create a network: `docker network create <network_name>`- Connect a container to a network: `docker network connect <network_name> <container_id>`- Disconnect a container from a network: `docker network disconnect <network_name> <container_id>`

#### Volumes:
- List volumes: `docker volume ls`
- Create a volume: `docker volume create <volume_name>`
- Remove a volume: `docker volume rm <volume_name>`- Mount a volume to a container: `docker run -v <volume_name>:<container_path> ...`- Copy files between a container and the host: `docker cp <container_id>:<container_path> <host_path>`

#### Dockerfile:
- Build an image from a Dockerfile: `docker build -t <image_name> .`
- Specify the working directory in a Dockerfile: `WORKDIR <directory_path>`- Set the entrypoint in a Dockerfile: `ENTRYPOINT ["<command>"]`- Set the default command in a Dockerfile: `CMD ["<command>"]`
