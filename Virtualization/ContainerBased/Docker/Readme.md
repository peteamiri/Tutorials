## Docker Containers Overview

### What Are Containers?

At their core, **containers** are a revolutionary way to package and run software applications. They provide a consistent and lightweight environment for applications to execute, regardless of the underlying infrastructure. Here's a detailed exploration of what containers are:

1. **Definition**:
   - A **container** is a **standard unit of software** that bundles an application along with all its dependencies. It encapsulates everything needed for the application to run smoothly, including code, runtime, system tools, libraries, and configuration settings.
   - Think of containers as portable, self-contained units that can be easily moved across different computing environments.

2. **Container Image**:
   - The heart of containers lies in the **container image**. An image is a lightweight, standalone package that contains all the necessary components for an application.
   - Components within an image include:
     - Application code
     - Runtime (such as Node.js, Python, or Java)
     - System tools
     - System libraries
     - Configuration files
   - Images are read-only and serve as blueprints for creating containers.

3. **Runtime Transformation**:
   - When you run an image, it becomes a **container**. This transformation happens dynamically at runtime.
   - Docker containers, for instance, come to life when they run on the **Docker Engine**.

4. **Portability and Consistency**:
   - Containers ensure that your application behaves consistently across different environments—whether it's your local development machine, a staging server, or a production cluster.
   - The promise of portability means that you can confidently move containers between different hosts without worrying about compatibility issues.

5. **Advantages of Containers**:
   - **Standardization**: Containers adhere to industry standards, making them portable and predictable.
   - **Lightweight**: Containers share the host machine's OS kernel, eliminating the need for a separate OS per application. This efficiency translates to higher server utilization and cost savings.
   - **Isolation**: Containers isolate applications from their environment, ensuring uniform behavior even across development, testing, and production stages.
   - **Security**: Docker, in particular, provides robust isolation capabilities, making applications safer within containers.

6. **Containers Everywhere**:
   - Containers have permeated various domains:
     - **Linux and Windows**: Docker containers are equally at home on both Linux and Windows platforms.
     - **Data Centers**: Major data center vendors and cloud providers leverage container technology.
     - **Serverless**: Even serverless frameworks utilize Docker containers.

### Containers vs. Virtual Machines

To appreciate containers fully, let's compare them to traditional virtual machines (VMs):

1. **Resource Isolation**:
   - Both containers and VMs offer resource isolation, but their approaches differ:
     - **Containers**: Isolate at the application layer. Multiple containers share the host OS kernel.
     - **VMs**: Isolate at the hardware level. Each VM runs its own OS, consuming more resources.

2. **Efficiency and Portability**:
   - Containers win in terms of efficiency:
     - **Size**: Container images are typically small (tens of MBs), whereas VM images are much larger.
     - **Density**: Containers allow more applications per host, reducing the need for numerous VMs.
     - **Portability**: Containers are more portable due to their lightweight nature.

3. **Use Cases**:
   - **Containers**: Ideal for microservices architectures, continuous integration, and rapid deployment.
   - **VMs**: Better suited for legacy applications, complex setups, and scenarios requiring full OS isolation.

In summary, Docker containers have revolutionized software deployment by providing consistency, efficiency, and portability. Whether you're building cloud-native applications or managing legacy systems, understanding containers is essential in today's dynamic tech landscape.

### Additional information

(1) What is a Container? | Docker. https://www.docker.com/resources/what-container/.
(2) Docker overview | Docker Docs. https://docs.docker.com/get-started/overview/.
(3) What is Docker? - GeeksforGeeks. https://www.geeksforgeeks.org/introduction-to-docker/.


# Docker introduction

Docker is a platform and a set of tools designed to facilitate the creation, deployment, and running of applications within containers. Containers are lightweight, standalone, and executable packages that contain everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. Docker uses containerization technology to create and manage these containers.

Here are some key components and concepts related to Docker:

1. **Docker Engine**: The core component of Docker, responsible for building, running, and managing containers. It includes a server daemon (dockerd) and a command-line interface (CLI) tool (docker).

2. **Dockerfile**: A text file that contains instructions for building a Docker image. It specifies the base image, environment variables, dependencies, and commands needed to set up the containerized environment.

3. **Docker Image**: A read-only template used to create containers. It includes the application code, runtime, libraries, and dependencies. Images are built from Dockerfiles and can be shared and reused across different environments.

4. **Container**: An instance of a Docker image that is running as a process on the host machine. Containers are isolated from each other and from the host system, but they share the host's kernel. They can be started, stopped, moved, and deleted independently.

5. **Docker Hub**: A cloud-based registry service provided by Docker, where users can find, store, and distribute Docker images. It hosts a vast collection of public images, and users can also publish their own images to share with others.

6. **Docker Compose**: A tool for defining and running multi-container Docker applications. It uses a YAML file to configure the services, networks, and volumes needed for the application, simplifying the management of complex deployments.

Docker has become immensely popular in software development and DevOps due to its ability to streamline the development process, improve consistency across different environments, and enhance scalability and resource utilization. It's widely used for building, testing, and deploying applications in various environments, from development laptops to production servers and cloud platforms.

## How Does Docker Works

Docker works by utilizing containerization technology to package applications and their dependencies into isolated containers, which can then be run consistently across different environments. Here's a basic overview of how Docker works:

1. **Docker Engine Installation**: Docker Engine is the core component of Docker. It consists of the Docker daemon (`dockerd`), which runs on the host machine, and the Docker client (`docker`), which provides a command-line interface (CLI) for interacting with the daemon. Users typically install Docker Engine on their local development machines or on servers where they want to deploy applications.

2. **Creating Docker Images**: To create a Docker container, you first need to define a Docker image. This is done using a text file called a Dockerfile, which contains a set of instructions for building the image. The Dockerfile specifies things like the base image to use, any dependencies that need to be installed, environment variables, and commands to run when the container starts.

3. **Building Docker Images**: Once you have a Dockerfile, you use the `docker build` command to build the Docker image. This command reads the instructions in the Dockerfile and executes them, creating layers within the image for each instruction. Each layer represents a filesystem change, such as adding a file or running a command. Docker caches these layers to improve build performance and optimize image size.

4. **Running Docker Containers**: Once you have a Docker image, you can use the `docker run` command to create and start a Docker container based on that image. When you run a container, Docker creates an isolated environment for it, including its own filesystem, networking, and process space. The container runs as a process on the host machine, but it's isolated from other processes and containers.

5. **Container Lifecycle**: Docker provides commands for managing the lifecycle of containers. You can start, stop, restart, and delete containers using the `docker` CLI. You can also inspect containers to view their status, logs, and configuration.

6. **Container Orchestration**: In production environments, you often need to run multiple containers together as part of a larger application. Docker provides tools like Docker Compose and Docker Swarm for orchestrating multiple containers, managing their networking and storage, and scaling them up or down as needed.

Overall, Docker simplifies the process of packaging, distributing, and running applications by encapsulating them in lightweight, portable containers. This allows developers to build applications once and run them anywhere, from development laptops to production servers and cloud platforms, with consistent behavior and minimal overhead.

## How componenets

The Docker Engine is the core component of Docker that enables containerization. It consists of several parts that work together to manage containers and their execution. Here's an overview of how the Docker Engine works:

1. **Docker Daemon (`dockerd`)**:
   - The Docker daemon (`dockerd`) is a persistent process that runs in the background on the host system. It listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes.
   - The daemon handles tasks such as building Docker images, running containers, managing container lifecycle, and orchestrating communication between containers and the host system.
   - It interacts with the underlying operating system's kernel to create and manage lightweight, isolated execution environments called containers.

2. **Docker Client (`docker`)**:
   - The Docker client (`docker`) is a command-line interface (CLI) tool that allows users to interact with the Docker daemon via the Docker API.
   - Users issue commands to the Docker client to perform various operations such as building Docker images, running containers, managing volumes, and networking.
   - The Docker client communicates with the Docker daemon over a Unix socket or a network interface using the Docker Remote API.

3. **Docker Objects**:
   - Docker Engine manages several types of objects, including images, containers, volumes, networks, and plugins.
   - Images: Read-only templates used to create containers. They contain the application code, runtime, dependencies, and configuration needed to run an application.
   - Containers: Runnable instances of Docker images. They encapsulate the application and its dependencies, providing a consistent runtime environment across different systems.
   - Volumes: Persistent storage that can be mounted into containers. Volumes allow data to persist across container restarts and be shared between multiple containers.
   - Networks: Virtual networks that allow containers to communicate with each other and with other services on the same host or across hosts.

4. **Docker API**:
   - The Docker API defines a set of HTTP endpoints that allow external clients to interact with the Docker daemon.
   - The API provides endpoints for managing Docker objects, including images, containers, volumes, networks, and more.
   - The Docker client interacts with the Docker daemon via the Docker API, sending HTTP requests to perform operations on Docker objects.

Overall, the Docker Engine provides a platform for building, running, and managing containerized applications. It abstracts away the complexities of containerization, allowing developers and operators to focus on building and deploying applications without worrying about the underlying infrastructure.

## Docker Registry

A Docker registry is a repository for Docker images. It serves as a centralized location where Docker users can store and share their Docker images. Think of it as a library where Docker images can be uploaded, downloaded, and managed.

Here are some key points about Docker registries:

1. **Public Registries**: Docker Hub is the most popular public Docker registry. It hosts a vast collection of publicly available Docker images, including official images maintained by Docker and community-contributed images. Docker users can search for images on Docker Hub, pull them to their local machines, and use them to run containers.

2. **Private Registries**: Organizations often have the need to store Docker images privately, either because they contain proprietary code or because they need to control access to the images. Docker allows users to set up private Docker registries, either on-premises or in the cloud, using tools like Docker Trusted Registry (DTR), Amazon Elastic Container Registry (ECR), or Google Container Registry (GCR). Private registries provide similar functionality to Docker Hub but with access control mechanisms to restrict who can push and pull images.

3. **Pushing and Pulling Images**: Docker users can use the `docker push` command to upload their Docker images to a registry and the `docker pull` command to download images from a registry to their local machines. This allows for easy sharing and distribution of Docker images across different environments and teams.

4. **Versioning**: Docker registries support versioning of images, allowing users to upload multiple versions of the same image and specify which version to pull when running containers. This enables developers to manage changes to their applications over time and roll back to previous versions if needed.

5. **Security**: Docker registries support authentication and authorization mechanisms to ensure that only authorized users can access and modify images. This helps prevent unauthorized access to sensitive information and ensures the integrity of the images stored in the registry.

Overall, Docker registries play a crucial role in the Docker ecosystem by providing a centralized location for storing and sharing Docker images, enabling collaboration, versioning, and secure distribution of containerized applications.

## Docker Swarm

Docker Swarm is Docker's native clustering and orchestration tool. It allows users to create and manage a cluster of Docker hosts, enabling them to deploy and scale containerized applications across multiple machines. Docker Swarm provides a simple yet powerful way to orchestrate containers, offering features for service discovery, load balancing, scaling, and high availability.

Key features of Docker Swarm include:

1. **Cluster Management**: Docker Swarm allows users to create a cluster of Docker hosts, known as a swarm. The swarm consists of one or more manager nodes and one or more worker nodes. Manager nodes are responsible for orchestrating the deployment and management of services, while worker nodes execute the tasks assigned to them.

2. **Service Deployment**: Docker Swarm uses the concept of services to define and deploy containerized applications. A service is a declarative configuration that specifies the desired state of a containerized application, including the number of replicas, resource constraints, networking settings, and more. Docker Swarm ensures that the specified number of containers is running across the cluster, automatically distributing them across available nodes.

3. **Load Balancing**: Docker Swarm provides built-in load balancing for services running on the cluster. Incoming requests are automatically distributed among the containers running the service, ensuring high availability and scalability. Docker Swarm uses an ingress network and a routing mesh to route traffic to the appropriate containers, making it easy to expose services to external clients.

4. **Service Discovery**: Docker Swarm includes built-in service discovery capabilities, allowing containers within the swarm to communicate with each other by their service name. Docker Swarm maintains a centralized service registry, which maps service names to the IP addresses and ports of containers running the service. This makes it easy for containers to discover and connect to other services within the swarm.

5. **Scaling**: Docker Swarm supports scaling applications horizontally by increasing or decreasing the number of replicas for a service. Users can scale services up or down manually using the Docker CLI or API, or they can configure auto-scaling based on metrics such as CPU usage or incoming requests. Docker Swarm automatically schedules and distributes additional containers across the cluster to handle increased demand.

6. **High Availability**: Docker Swarm ensures high availability for containerized applications by automatically restarting containers that fail or become unavailable. Manager nodes monitor the health of containers and nodes in the swarm, taking corrective actions to maintain application availability. In the event of a manager node failure, Docker Swarm uses leader election to elect a new manager and maintain continuity of service.

Overall, Docker Swarm provides a simple and integrated solution for clustering and orchestrating containerized applications, making it easy to deploy, manage, and scale containers across a cluster of Docker hosts. It is well-suited for organizations looking for a lightweight and easy-to-use container orchestration tool with built-in support for Docker containers.

## Docker Orchastration

Docker orchestration refers to the process of managing, deploying, and scaling containerized applications across a cluster of machines. It involves automating various tasks related to container deployment, networking, load balancing, scaling, and service discovery to ensure that containerized applications run efficiently, reliably, and at scale. Orchestration frameworks help manage the complexity of deploying and managing distributed applications composed of multiple containers.

Key aspects of Docker orchestration include:

1. **Container Deployment**: Orchestration frameworks automate the deployment of containers across a cluster of machines. They handle tasks such as scheduling containers to run on specific nodes, pulling images from registries, and starting containers with the appropriate configuration.

2. **Networking**: Orchestration frameworks manage networking for containerized applications, ensuring that containers can communicate with each other and with external services. They provide features such as virtual networks, service discovery, and load balancing to facilitate communication between containers.

3. **Service Discovery**: Orchestration frameworks enable service discovery, allowing containers to discover and communicate with each other dynamically. They maintain a centralized registry of available services and their locations, making it easy for containers to find and connect to each other.

4. **Scaling**: Orchestration frameworks support scaling applications horizontally by adding or removing container instances based on demand. They monitor resource utilization and can automatically scale the number of containers to handle fluctuations in workload.

5. **Load Balancing**: Orchestration frameworks distribute incoming traffic across multiple instances of a containerized application to ensure high availability and performance. They provide built-in load balancing capabilities or integrate with external load balancers to evenly distribute traffic across containers.

6. **Fault Tolerance**: Orchestration frameworks ensure the fault tolerance of containerized applications by automatically restarting failed containers and rescheduling them to healthy nodes. They monitor the health of containers and nodes, taking corrective actions to maintain application availability.

Popular Docker orchestration frameworks include:

- **Docker Swarm**: Docker's built-in orchestration tool, which provides a simple and integrated solution for deploying and managing containerized applications across a cluster of Docker hosts.

- **Kubernetes**: An open-source container orchestration platform originally developed by Google, now maintained by the Cloud Native Computing Foundation (CNCF). Kubernetes is highly scalable and offers a rich set of features for managing containerized applications in production environments.

- **Apache Mesos**: A distributed systems kernel that abstracts CPU, memory, storage, and other computing resources across a cluster of machines. Mesos can run Docker containers alongside other types of workloads and provides a flexible framework for building custom orchestration solutions.

Overall, Docker orchestration simplifies the deployment and management of containerized applications, allowing organizations to leverage the benefits of containerization while ensuring scalability, reliability, and performance.

### Configuring Docket Swarm

Configuring Docker Swarm involves setting up a cluster of Docker hosts, initializing the swarm, joining nodes to the swarm, and configuring various settings to manage and deploy containerized applications. Here's a step-by-step guide to configuring Docker Swarm:

1. **Set Up Docker Hosts**:
   Ensure that you have multiple machines running Docker Engine. These machines will serve as nodes in the Docker Swarm cluster. Install Docker Engine on each host following the official Docker documentation specific to your operating system.

2. **Initialize the Swarm**:
   On one of the Docker hosts, initialize the Docker Swarm to create the first manager node. Open a terminal or SSH into the host and run the following command:
   ```
   docker swarm init --advertise-addr <MANAGER_IP>
   ```
   Replace `<MANAGER_IP>` with the IP address of the host. This command initializes the swarm and generates a join token, which you'll use to add additional nodes to the swarm.

3. **Join Worker Nodes**:
   On the remaining Docker hosts, join them to the swarm as worker nodes using the join token obtained from the previous step. Run the following command on each worker node:
   ```
   docker swarm join --token <TOKEN> <MANAGER_IP>:<PORT>
   ```
   Replace `<TOKEN>` with the join token generated during swarm initialization, `<MANAGER_IP>` with the IP address of the manager node, and `<PORT>` with the port number (usually 2377).

4. **Verify Swarm Status**:
   After joining all nodes, return to the manager node and verify the status of the Docker Swarm using the following command:
   ```
   docker node ls
   ```
   This command should list all nodes in the swarm, including the manager and worker nodes.

5. **Configure Swarm Settings**:
   You can configure various settings for the Docker Swarm, such as replication factors, service constraints, network settings, and more. Use Docker commands or Docker Compose files to define the desired configurations.

6. **Deploy Services**:
   Now that the Docker Swarm is configured, you can deploy containerized applications as services. Define the desired state of the services using Docker Compose files or Docker service commands, specifying parameters such as image, replicas, ports, networks, and volumes.

7. **Monitor and Manage the Swarm**:
   Use Docker commands to monitor and manage the Docker Swarm cluster. You can view service and node status, inspect containers, scale services, update configurations, and perform other administrative tasks using the Docker CLI.

8. **Backup and Disaster Recovery**:
   Implement backup and disaster recovery strategies to ensure the resilience of the Docker Swarm cluster. Regularly backup swarm configurations, data volumes, and critical data to prevent data loss and minimize downtime in case of failures.

By following these steps, you can configure Docker Swarm and set up a cluster of Docker hosts for orchestrating and managing containerized applications at scale.

## Docker Swarm Architect

The architecture of Docker Swarm, Docker's native clustering and orchestration tool, is designed to provide a highly available and scalable platform for deploying and managing containerized applications across a cluster of Docker hosts. Here's an overview of the Docker Swarm architecture:

1. **Manager Nodes**:
   - Manager nodes are responsible for controlling the Docker Swarm cluster and orchestrating containerized applications.
   - Each Docker Swarm cluster must have at least one manager node, but it can have multiple manager nodes for high availability.
   - Manager nodes maintain the state of the swarm, handle service deployment and scaling, and manage the membership of worker nodes.
   - Manager nodes use the Raft distributed consensus algorithm to ensure consistency and fault tolerance across the cluster.

2. **Worker Nodes**:
   - Worker nodes are responsible for running the tasks and services assigned to them by the manager nodes.
   - Worker nodes execute containerized applications and provide computing resources such as CPU, memory, and storage.
   - Docker Swarm automatically distributes tasks and services across worker nodes to balance the workload and maximize resource utilization.

3. **Swarm State**:
   - Docker Swarm manager nodes maintain the state of the swarm, including information about services, tasks, nodes, and configurations.
   - The swarm state is stored locally on each manager node and replicated across all manager nodes using the Raft consensus algorithm.
   - Raft ensures that the swarm state remains consistent and available even in the event of manager node failures or network partitions.

4. **Service Discovery**:
   - Docker Swarm provides built-in service discovery capabilities, allowing containers within the swarm to communicate with each other by their service name.
   - Docker Swarm maintains a centralized service registry, which maps service names to the IP addresses and ports of containers running the service.
   - Service discovery enables seamless communication between containers and allows applications to dynamically scale and adapt to changes in the swarm.

5. **Load Balancing**:
   - Docker Swarm includes built-in load balancing for services running on the cluster.
   - Incoming requests are automatically distributed among the containers running the service, ensuring high availability and scalability.
   - Docker Swarm uses an ingress network and a routing mesh to route traffic to the appropriate containers, making it easy to expose services to external clients.

6. **Overlay Networking**:
   - Docker Swarm supports overlay networking, allowing containers to communicate with each other across different nodes in the swarm.
   - Overlay networks provide a virtual network abstraction that spans the entire swarm, enabling seamless communication between containers running on different hosts.

Overall, the architecture of Docker Swarm is designed to provide a scalable, resilient, and easy-to-use platform for deploying and managing containerized applications. By distributing tasks and services across multiple nodes and providing built-in features for service discovery, load balancing, and networking, Docker Swarm simplifies the process of orchestrating containers at scale.






### Learn More About Docker
* [Docker Official Documentation](https://docs.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/)
* [Tutorial](https://rominirani.com/docker-tutorial-series-a7e6ff90a023)
* [Good Starting Point](https://www.youtube.com/watch?v=wxxigbHwDGM&list=PL2We04F3Y_42mOz2jsBqB_TOGIgaB8KkL)
* [Docker Commands](https://www.edureka.co/blog/docker-commands/)
* [Docker Resources](https://www.janbasktraining.com/blog/what-is-docker/)
* [Docker](https://www.youtube.com/watch?v=zJ6WbK9zFpI)
* [Docker](https://www.youtube.com/watch?v=1xo-0gCVhTU)

# Docker
* [IBM Containers](https://www.youtube.com/watch?v=0qotVMX-J5s)
* [Docker Vs. Kubernaties](https://www.youtube.com/watch?v=2vMEQ5zs1ko)

# Docker Hub

* <a href="https://hub.docker.com/" target="_blank">Docker Hub</a>

# Docker:
The followings are some of the docker cli commands;

```
docker infor
docker login docker.io
docker images
docker containsers
docker ps
docker logs
docker exec -it imageName bash
docker cp filename containername:full_path/filename

```
### Dockerfile

### docker-compose.yml

```
docker-compose up -d       #creates the service
docker-compose stop
docker-compose start
docker-compose restart
docker-compose down        #deletes the entrie images
```

```
version 3
services:
  jenkins:
    container_name:
    images:
    ports:
      - "8080:8080"
    volumes:
    networks:
networks:
  net:

```

### Installation

* <a href="https://computingforgeeks.com/install-docker-and-docker-compose-on-rhel-8-centos-8/" target="_blank">Installing Docker on CentOS 8</a>

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

### For more information see

* <a href="https://www.youtube.com/watch?v=fqMOX6JJhGo" target="_blank">Youtube Introduction to Docker Course</a>

## Important Subjects in Docker
* Dockerfile
  - Layers
* Docker Compose
* Docker Swarm
* Docker Orchastration
* Image vs. Container
  - Image is like Class in object orirented
  - Contrainer is similar to objects in Object Oriented environement
	- Information that is created within the containter only lasts during the lifetime of container.
	- Images are generally created using docker file. the informaiton in the images last for the life of image.

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

## Setting up Docker repository
## Docker repository / registry

Docker registry could be hosted by a third party, as public or private registry, like one of the following registries:

* Docker Hub
* Quay
* Google Container Registry
* AWS Container Registry

or you can host the docker registry by yourself (see https://docs.docker.com/docker-trusted-registry/ for more details).

Docker repository is a collection of different docker images with same name, that have different tags. Tag is alphanumeric identifier of the image within a repository.

For example see https://hub.docker.com/r/library/python/tags/. There are many different tags for the official python image, these tags are all members of the official python repository on the Docker Hub. Docker Hub is a Docker Registry hosted by Docker.

#### To find out more read:

* [Docker Registry](https://docs.docker.com/registry/)
* [Github Repository](https://github.com/docker/distribution)
* [Blog](https://nickjanetakis.com/blog/docker-tip-53-difference-between-a-registry-repository-and-image)
