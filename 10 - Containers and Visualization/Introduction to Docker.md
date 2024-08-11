# Introduction to Docker

## 1. What is Docker?
Docker is an open-source platform that automates the deployment of applications inside lightweight, portable containers. Containers package an application with all its dependencies, ensuring consistency across different environments.

## 2. Why Use Docker?
- **Consistency:** Applications run the same way regardless of where they're deployed.
- **Isolation:** Each container runs in its own environment, preventing conflicts.
- **Efficiency:** Containers are lightweight and use fewer resources than traditional virtual machines.
- **Scalability:** Easily scale applications by spinning up multiple containers.
- **Version Control:** Docker images can be versioned, allowing for easy rollbacks.

## 3. Key Docker Concepts
- **Images:** Read-only templates used to create containers.
- **Containers:** Runnable instances of images.
- **Dockerfile:** A script of instructions to build a Docker image.
- **Docker Hub:** A repository of Docker images.

## 4. Installing Docker on Linux Mint

### 1. Update Your System:
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Dependencies:
```bash
sudo apt install -y apt-transport-https ca-certificates curl gnupg software-properties-common
```

### 3. Add Docker's GPG Key:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### 4. Set Up the Docker Repository:
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 5. Install Docker:
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```

### 6. Verify Installation:
```bash
sudo docker run hello-world
```

### 7. (Optional) Add Your User to the Docker Group:
```bash
sudo usermod -aG docker $USER
newgrp docker
```

## 5. Basic Docker Commands
- **Run a Container:** `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`
- **List Running Containers:** `docker ps`
- **Stop a Container:** `docker stop [CONTAINER_ID]`
- **Remove a Container:** `docker rm [CONTAINER_ID]`
- **List Images:** `docker images`
- **Pull an Image:** `docker pull [IMAGE_NAME]`
- **Build an Image:** `docker build -t [IMAGE_NAME] [PATH_TO_DOCKERFILE]`

## 6. Docker Best Practices
1. Use official images as base images when possible.
2. Keep your images small by using multi-stage builds and minimizing layers.
3. Use environment variables for configuration.
4. Don't run containers as root user.
5. Regularly update your Docker images and host system.

## 7. Troubleshooting
- If you encounter permission issues, ensure your user is in the docker group.
- For networking issues, check your firewall settings.
- Use `docker logs [CONTAINER_ID]` to view container logs for debugging.

For more detailed information, refer to the [official Docker documentation](https://docs.docker.com/).