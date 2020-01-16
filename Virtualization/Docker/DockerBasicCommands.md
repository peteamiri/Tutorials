### Basic commands

##### `docker run`

Docker run is probably the most important command on this Docker list. It creates a new container, then starts it using a specified command. It is the equivalent of using docker create and then immediately using docker start (we‘ll go through those below).

```
  Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
Example:

```
  docker run hello-world
```
This example will download, create and run the ‘hello-world’ container from docker hub.

##### `docker create`

This command creates a new container and prepares it to run the specified command, but doesn’t run it. The ID is printed to STDOUT. This command is similar to docker run, but the container is never started. It can be started at any time with docker start <container_id>.

This can be useful if you want to create and prepare a container for running at a later time.

```
Usage: docker create [OPTIONS] IMAGE [COMMAND] [ARG...]
```

Example:
```
docker create hello-world
```


This will download and create the hello-world container same as above, but it won’t run it.

##### `docker start`

Starts container, either created with docker create or one that was stopped.

```
Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

Example:

```
docker start hello-world
```

##### `docker stop`

Stops a running container.

```
Usage: docker stop [OPTIONS] CONTAINER [...]
```
Example:
```
docker start hello-world
```
This example will stop the container we started in the example above. You can use docker start to start it back up again.

##### `docker ps`

Use this command to list the docker containers available. By default, only running ones are listed, but you can add options such as -a to get a docker container list. More info

```
Usage: docker ps [OPTIONS]
```
Example:
```
docker ps -a
```

The above command will display all containers on your system.


##### `docker rm`

Removes a container. Once you use docker ps to list available containers, you can use this command to remove one or more of them.

```
Usage: docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

Example:
```
docker rm -f redis
```
This example will remove the container called ‘redis’. The -f tag forces the action, meaning the container will receive a SIGKILL command first.

##### `docker rmi`

`rmi` stands for remove image. Similar to docker rm but removes the docker image rather than a running instance of an image (called a container).

```
Usage: docker rmi [OPTIONS] IMAGE [IMAGE...]
```

Example:
```
docker rmi test
```
This example will remove the image name ‘test’. Use the docker images command to get a list of images and ids.

##### `docker login`

Let’s you login to a docker registry. You can use this command to log into any public or private registry. You’ll probably use this to log into Docker Hub.

```
Usage: docker login [OPTIONS] [SERVER]
```

Example:
```
docker login localhost:8080
```
Here we are logging into a self-hosted registry by specifying the server name. Otherwise, just use docker login to login to your Docker Hub registry.

To loging to the docker hub use the following command;

```
docker login "https://index.docker.io/v1"
```
you will be prompted for user id and password.

The information regarding the repositories are stored at `/etc/containers/registries.conf`

##### `docker tag`
Description: Use this command to create a tag TARGET_IMAGE that refers to SOURCE_IMAGE.

Usage:

```
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```

Example:
```
docker tag 7d9495d03763 maryatdocker/docker-whale:latest
```

Here we are tagging a local image with ID “7d9495d03763″ into the “maryatdocker/docker-whale” repository with the tag “latest”


##### `docker push`

docker push is the command you’ll use to share your images to Docker Hub or another registry. It’s a key part of the deployment process, and you’ll need to use it with docker tag and docker login to work properly.


Usage:
```
docker push [OPTIONS] NAME[:TAG]
```

Example:
```
docker push maryatdocker/docker-whale
```
This example will push the image we tagged above to the repository. It’s actually the example from the docs, check out the full page here.


##### `docker exec`

The exec command can be used to run a command in a container that already running. docker run lets us run a command when starting a container, docker exec can be used to feed subsequent commands to a container.

Usage:
```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
Example:

First start a container with
```
docker run --name ubuntu_bash --rm -i -t ubuntu bash
```
Now we can execute a command on that container to create a new file with
```
docker exec -d ubuntu_bash touch /tmp/execWorks
```


##### `docker logs`
Description: Getting deeper into using docker, the docker logs command lets you see the log file for a running container. However, it can only be used with containers that were started with the json-file or journald logging driver

Usage:
```
docker logs [OPTIONS] CONTAINER
```
Example:
```
docker logs -f MyCntr
```

##### `docker kill`

Sometimes you just need to kill one or all running containers. Similar to SIGKILL (this is actually the message it will receive), docker kill will stop a container running.

Usage:
```
docker kill [OPTIONS] CONTAINER [CONTAINER...]
```
Example:
```
docker kill MyCntr
```

##### `docker swarm`

Use docker swarm to manage a swarm. You can initialize a swarm, add manager and worker nodes, and update a swarm. This command is actually a whole bunch of commands in one – take a look at all of the child commands here.

Example:
```
docker swarm init --advertise-addr <MANAGER-IP>
```

This will initialize a swarm and give us back the address to add workers to the swarm later. For a better understanding of how to use docker swarms, take a look at the create a swarm tutorial on the docs.
