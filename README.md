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

Assure that you're logged in: docker login
Build docker image: docker build -t docker_demo .
Run the container: docker run -p 5000:5000 docker_demo
(Map the docker image's 5000 port to system's 5000 port)
Tag your image: docker tag docker_demo:latest wildchaser1703/docker_demo:v1
Push image to dockerhub: docker push wildchaser1703/docker_demo:v1
Pull image to dockerhub: docker pull wildchaser1703/docker_demo:v1
Run the pulled image: docker run -p 5000:5000 wildchaser1703/docker_demo:v1

#### Difference between Docker Image and Docker Container
- Image: A static snapshot (immutable); Describes the filesystem and startup instructions (CMD, ENTRYPOINT) (Hint: Think of a foldable tent with materials)
- Container: A runtime instance of that image; Runs as a lightweight process isolated from your system (Hint: Think of building the whole tent using those materials)
