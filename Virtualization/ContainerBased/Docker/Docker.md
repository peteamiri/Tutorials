# Docker

* install docket CLI `sudo yum install docket -y`
* validate installation of CLI : `docker info`
* find docker version of CLI: `docker --version`


### Sample Help


* geting more help : `docker --help`

Help output

```
Usage:	docker COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default
                           "C:\Users\Pete\.docker")
  -D, --debug              Enable debug mode
      --help               Print usage
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level
                           ("debug"|"info"|"warn"|"error"|"fatal")
                           (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default
                           "C:\Users\Pete\.docker\ca.pem")
      --tlscert string     Path to TLS certificate file (default
                           "C:\Users\Pete\.docker\cert.pem")
      --tlskey string      Path to TLS key file (default
                           "C:\Users\Pete\.docker\key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  container   Manage containers
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.
```


## Dockerfile

#### Lesson One Introduction to Docker CLI commands

* All commands run under docker shell CLI
* `docker ps` list all aviailable containers that are currently running
* Commands follow the general guidlines: `docket <arguments> <image name> <commands to run under the image>`
* `docker ps --help`
* `docker ps -a` displays all the running containers
* `docker build --help`
* `docker run --help` displays all the options for the run command
* most common arguments are `-i` : interactive `-t` : terminal
* for most run commands netwrok port translation must be set using this guideline `-p <containter_port>:<host_port>`. this flag translates the containtere_port to the host_port.
* `-v <host absolut_path>:<docker_image_mount>` (I have not been able to make this work. it gives me permission denied error as root, and it does not allow changing permissions).
  - example: `docker run -it -p1234:80 -v ${PWD}/.:/home/test demo`

#### Lesson Two

* run `docker pull hello-world`
* run `docker run hello-world`
* The above command perform the following tasks:
  1. `Docker Client (CLI)` connects to `Docker Daemon`
  2. `Docker daemon` checks for immage if it does not exists it pulls it from `Docer HUB`
  3. `Docker daemon` converts the `image` to `container`, by executing it.
  4. `Docker daemon` sent outputs from the contaainers to the `docker client`

#### Session

* most used commands are `ps`, `build`, `run`, `images`
* Each image has a tag associated with it.

#### Session

* create a doctectory,
* create a file `Docketfile` exact name and casing.
* First line generally is `From` defines the type of host and destination operating system.
* run `docker build -t demo` will create an image named demo
* run `docker run -it demo` will runs an interactive session of the container named demo
* run `exit` to exit from the image
