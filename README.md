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

docker rmi <image>        # Remove image

docker rm <container-id> # You cannot remove an image if a container is currently using it. You may need to stop and remove the associated containers first:


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
