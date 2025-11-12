# Docker_Demo
### Docker Benefits:
#### 1. Portability
Docker containers can run consistently across different environments (development, testing, production) without any platform differences. For example, a container running on your laptop will work the same on a cloud server.

#### 2. Isolation
Each Docker container is isolated from others. This is useful when running multiple servers or apps on the same machine without worrying about the compatibility issues.

#### 3. Scalability
Docker makes scaling apps easier. For example, if a web service is getting high traffic, you can easily add more containers and handle the load. When the load subsides, you can remove the container to save the resources.

### Docker vs VM
Docker is lighter, faster, and more portable as compared to VMs, which are heavier and slower due to full OS virtualization.

Docker shares the host OS and use fewer resources, making it lightweight. VM runs on a full OS for each instance, making it heavy and slower to start (minutes). It consumes more resources beacuse it needs to virtualize hardware, not just the app.

### Dockerfile
A text file which has instructions on how to build a Docker image. It's a blueprint for the image, specifying the environment, app and dependencies.
#### Key Components:
1. FROM: Specifies the base image.
2. COPY or ADD: Adds file from your host system into the image.
3. RUN: Executes commands in the image, such as installing the software.
4. CMD or ENTRYPOINT: Defines the command that runs when the container starts.
5. EXPOSE: Specifies the port the container will listen on.

#### Steps to implement the Dockerfile
1. Install Docker Desktop
2. Sign into Dockerhub and Docker Desktop
3. Docker Desktop:
- Check docker install: cli -> "docker"
- Pull the hello world image and run it

4. Assure that you're logged in: docker login
5. Build docker image: docker build -t docker_demo .
6. Run the container: docker run -p 5000:5000 docker_demo (Map the docker image's 5000 port to system's 5000 port)
7. Tag your image: docker tag docker_demo:latest wildchaser1703/docker_demo:v1
8. Push image to dockerhub: docker push wildchaser1703/docker_demo:v1
9. Pull image to dockerhub: docker pull wildchaser1703/docker_demo:v1
10. Run the pulled image: docker run -p 5000:5000 wildchaser1703/docker_demo:v1

#### Difference between Docker Image and Docker Container
- Image: A static snapshot (immutable); Describes the filesystem and startup instructions (CMD, ENTRYPOINT) (Hint: Think of a foldable tent with materials)
- Container: A runtime instance of that image; Runs as a lightweight process isolated from your system (Hint: Think of building the whole tent using those materials)

#### Docker Engine
Docker engine is the core technology that powers Dockers, consisting of 3 main parts:
 - Docker Daemon (Server): Background service running on the host machine. Responsible for managing containers, images, networks, etc. Daemon listens to API requests and performs the actions you request.
 - REST API: Allows the communication between Daemon and the client. You can use the API to interact with Docker to create containers or images.
 - Docker CLI (Client): CLI allows you to interact with Docker.  

 #### Docker Image
 It is a lightwweight, standalone, and executable package that includes everything needed to run a piece of software. It is read-only and used to create containers.
 Components of a Docker Image:
 - Base Image: This is the starting point, usually a minimal OS or runtime.
 - Layers: Each change (like installing software, adding files) in the image adds a new layer. Docker uses a layered filesystem, so layers are stacked to form the final image.
 - Metadata: Contains information like the image's size, creation date, and instructions (like CMD or ENTRYPOINT) on how to run the container.

 #### Docker Image Lifecycle
 - Creation: Build a new image using a Dockerfile or pull one from a registry (docker pull). 
 - Storage: Images are stored locally in your Docker environment and can be pushed to remote properties like Docker Hub.
 - Distribution: Images can be shared or distributed by pushing them to a public/private registry, where others can pull and use them.
 - Execution: When you run a Docker image, a container is creation. This container is the live instance of the image. 

 #### Docker Container
 A Docker container is a lightweight, isolated, and executable environment created from a Docker image. It packages the application and all its dependencies, ensuring it runs consistently in any environment.

 Key Features:
 - Isolation: Each container runs independently with its own filesystem and resources.
 - Ephemeral: Containers can be started, stopped or destroyed easily.
 - Lightweight: Conatiners share the host OS kernel, making them faster and less resource-intensive than VMs. 