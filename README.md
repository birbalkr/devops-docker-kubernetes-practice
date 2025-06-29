# 🚀 DevOps Docker & Kubernetes Practice

![GitHub last commit](https://img.shields.io/github/last-commit/birbalkr/devops-docker-k8s-practice?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/birbalkr/devops-docker-k8s-practice?color=blue)
![GitHub issues](https://img.shields.io/github/issues/birbalkr/devops-docker-k8s-practice?style=flat-square)
![GitHub pull requests](https://img.shields.io/github/issues-pr/birbalkr/devops-docker-k8s-practice?style=flat-square)

> A hands-on DevOps lab for learning Docker and Kubernetes (K8s) with real-world examples, CI/CD integration, and system orchestration practices.

---

## 🐳 Docker Commands Cheat Sheet

### 🔹 Docker Basics

```bash
docker --version          # Check Docker version
docker info               # Display Docker system-wide information
docker help               # Show help for Docker commands
```

---

### 🔹 Working with Images

```bash
docker images             # List Docker images
docker build -t <name> .  # Build image from Dockerfile in current directory <name>

docker build: Command to build a Docker image.
    -t <image-name>: Tags the image with a name (e.g., myapp:latest).
    .  The dot refers to the build context, typically the current directory containing the Dockerfile.

docker pull <image>       # Download image from Docker Hub for Ex: docker pull mysql

docker rm <container-id> # You cannot remove an image if a container is currently using it. You may need to stop and remove the associated containers first:

docker rmi <image>        # Remove image

    rmi: Stands for "remove image".
    <image-name-or-id>: # The name or ID of the image you want to delete.

    Example: docker rmi myapp:latest

docker image prune -a  # To remove all unused images:


docker tag <image> <tag>  # Tag image with a new name

    docker tag: Creates a new tag (alias) for an existing image.
    <image>: The name or ID of the existing image.
    <repository>:<tag>: The new name and optional tag for the image.

    Example:  docker tag myapp:latest myusername/myapp:v1.0


## This command tags the local image myapp:latest with a new name myusername/myapp:v1.0, typically used before pushing to Docker Hub or another registry.

docker push myusername/myapp:v1.0

```

---

### 🔹 Working with Containers

```bash

docker run <image>             # Run container from image
    docker run: Creates and starts a new container from the specified image.
    <image>: The image name (optionally with a tag like myapp:latest).

    Example: docker run myapp.

docker run -it <image>         # Run interactively
    -i: Keep STDIN open even if not attached.
    -t: Allocate a pseudo-TTY '(terminal)'.
    Combined as -it, this allows you to interact with the container via the terminal.

    # when you want to run a container and interact with it, e.g., start a shell inside a base image. it's also essential when running a containerized program that requires user input (e.g. read in shell scripts, prompts in Python, etc.).

    Example:
        docker run -it myapp

docker run -d <image>          # Run in detached mode

    -d stands for detached mode.
    This runs the container in the background and prints the container ID.

    Example:
    docker run -d myapp.

docker ps                      # List running containers / Shows all currently running Docker containers.

    # CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS       PORTS                    NAMES
    # a1b2c3d4e5f6   nginx     "nginx -g 'daemon   2 hours ago   Up 2 hours   0.0.0.0:8080->80/tcp     my-nginx


docker ps -a                   # List all containers / To list all containers (running and stopped) Includes containers that have exited, been stopped, or failed.

docker stop <container>        # Stop a running container / Stops a running container gracefully. You can use the container ID or name.
    Example:
        docker stop myapp

docker start <container>       # Start a stopped container / Starts a container that was previously stopped.
    Example:
    docker start myapp

docker restart <container>     # Restart a container /Stops and then starts the container again. Useful for applying changes like updated environment variables or configs.

    Example:
    docker restart myapp

docker rm <container>          # Remove a container / Removes a stopped container from your system.
    Example:
        docker rm myapp

docker exec -it <container> bash  # Open bash in running container
```

---

## 📚 What You'll Learn

- ✅ Core Docker concepts (images, containers, networks, volumes)
- ✅ Writing and optimizing Dockerfiles
- ✅ Using Docker Compose for multi-service apps
- ✅ Kubernetes essentials (Pods, Deployments, Services, ConfigMaps)
- ✅ Running Kubernetes locally with Minikube
- ✅ CI/CD using GitHub Actions (coming soon)
- ✅ Helm basics (optional, coming soon)
- ✅ Container security and monitoring tools (Prometheus, Grafana - planned)

---

## 🧰 Tech Stack

| Tool                | Purpose                     |
| ------------------- | --------------------------- |
| **Docker**          | Containerization engine     |
| **Docker Compose**  | Manage multi-container apps |
| **Kubernetes**      | Container orchestration     |
| **Minikube**        | Local K8s cluster           |
| **kubectl**         | K8s command-line interface  |
| **GitHub Actions**  | CI/CD pipelines             |
| **Helm** (optional) | K8s package manager         |
| **Shell Scripting** | Automation tasks            |

---

## 📁 Folder Structure

```bash
.
├── demo-docker-app/        # Docker basics and examples
├── k8s-manifests/          # Kubernetes YAML manifests
├── cicd-pipelines/         # GitHub Actions workflows
├── assets/                 # Images and visual content
├── projects/               # Sample mini-projects
└── README.md               # This file
```
