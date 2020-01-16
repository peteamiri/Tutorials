# Docker
* [Docker Official Documentation](https://docs.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/)
* [Tutorial](https://rominirani.com/docker-tutorial-series-a7e6ff90a023)
* [Docker Coommands](https://www.edureka.co/blog/docker-commands/)
* [Docker Resources](https://www.janbasktraining.com/blog/what-is-docker/)
* [Docker](https://www.youtube.com/watch?v=zJ6WbK9zFpI)
* [Docker](https://www.youtube.com/watch?v=1xo-0gCVhTU)

# Docker
* [IBM Containers](https://www.youtube.com/watch?v=0qotVMX-J5s)
* [Docker Vs. Kubernaties](https://www.youtube.com/watch?v=2vMEQ5zs1ko)

# Linux Kernel
	* [Linux Kernel](http://www.win.tune.nl/~aeb/linux/lk.html)

# Docker Hub

* [Docker Hub](https://hub.docker.com/)

# Docker:

### Installation

* [Docker](https://computingforgeeks.com/install-docker-and-docker-compose-on-rhel-8-centos-8/)


### Docker Components / Terminologies

There area a number of Docker specific jargon that we need to clarify before diving into installation and usage examples. Below are commonly used terminologies in Docker ecosystem.

* `Docker daemon`: This is also called Docker Engine, it is a background process which runs on the host system responsible for building and running of containers. The background service running on the host that manages building, running and distributing Docker containers. The daemon is the process that runs in the operating system which clients talk to.

* `Docker Client`: This is a command line tool used by the user to interact with the Docker daemon. The command line tool that allows the user to interact with the daemon. More generally, there can be other forms of clients too - such as Kitematic which provide a GUI to the users.

* `Docker Image`: An image is an immutable file that’s essentially a snapshot of a container. A docker image has a file system and application dependencies required for running applications. The blueprints of our application which form the basis of containers.

* `Docker container`: This is a running instance of a docker image with an application and its dependencies. Each container has a unique process ID and isolated from other containers. The only thing containers share is the Kernel. Containrs are created from Docker images and run the actual application.

* `Docker registry or Docker HUB`: This is an application responsible for managing storage and delivery of Docker container images. It can be private or public.  It is registry of Docker images. You can think of the registry as a directory of all available Docker images. If required, one can host their own Docker registries and can use them for pulling images.


### Two editions of Docker available.

* `Community Edition (CE)`: ideal for individual developers and small teams looking to get started with Docker and experimenting with container-based apps.

* `Enterprise Edition (EE)`: Designed for enterprise development and IT teams who build, ship, and run business-critical applications in production at scale.


# Linux Containers
	1- Container vs. Virtual Machines
	2- Kernel Namespace
	2- User Space
	2- Kernel Space
	2- Usr Mode vs. Kernel Mode
	3- cgrou* ps
	4- Capabilities

# Docker Engine
	Execution Driver: libcontainer vs. LXC
	AUFS
	OverlayFS
	Device Mapper

# Docker Images
	docker build
	docker images
	docker inspect
	Union mounts
	layering
	Dockerfile

# Docker Containers
* docker start|stop|restart
* Registries
* Volumes
* Networking
* Cross-Platform

# Docker File
* File Structure
