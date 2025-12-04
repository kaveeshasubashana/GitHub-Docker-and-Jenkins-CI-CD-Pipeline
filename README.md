# CI/CD Pipeline with Docker, Jenkins, and GitHub

This is a simple Node.js project created to practice a full CI/CD workflow using GitHub, Docker, and Jenkins.
The project builds a Docker image, logs in to Docker Hub, and pushes the image automatically using a Jenkins pipeline.

## 🚀 Project Workflow (Pipeline Overview)

SCM Checkout → Jenkins pulls the code from GitHub

Build Docker Image → Jenkins builds a Docker image using the project Dockerfile

Login to Docker Hub → Using Jenkins credentials

Push Image → Image is uploaded to Docker Hub with the Jenkins build number

Post Actions → Logout from Docker Hub

The pipeline looks like this:

✔️ SCM Checkout
✔️ Build Docker Image
✔️ Login to Docker Hub
✔️ Push Image
✔️ Post Actions

<img width="1356" height="343" alt="image" src="https://github.com/user-attachments/assets/1955645e-d6c3-400a-b22b-38d48a553491" />


## 🛠️ Tech Stack

Node.js + Express.js

Docker

Jenkins Pipeline

GitHub

Supertest (for simple endpoint testing)


## 🐳 Docker Commands (Manual Use)
##### Build image:
```bash
docker build -t nodeapp .
```
##### Run container:
```bash
docker run -p 3000:3000 nodeapp
```

# ✔️ What I Learned

How to create an end-to-end CI/CD pipeline

How Jenkins automates Docker builds

How to use Jenkins credentials securely

How to push Docker images to Docker Hub automatically

Basic testing with Supertest
