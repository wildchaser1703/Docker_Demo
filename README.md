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
