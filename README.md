# nginxdemorepo 🚀

A simple Dockerized Nginx project that serves a custom HTML page, with a basic CI pipeline using GitHub Actions.

📌 Project Overview

This repository demonstrates how to:

Build a custom Docker image using Nginx
Serve a static HTML page using a container
Automate Docker image build using GitHub Actions CI

It uses:

🐳 Docker
🌐 NGINX
⚙️ GitHub Actions
📁 Project Structure
nginxdemorepo/
│
├── Dockerfile
├── index.html
└── .github/
    └── workflows/
        └── ci.yml
🐳 Docker Setup
Dockerfile
FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html
What it does:
Uses the official Nginx image
Replaces default webpage with your custom index.html
🌐 Web Page
index.html
<!DOCTYPE html>
<html>
<head>
   <title>My Docker Page</title>
</head>
<body>
   <h1>Hello Docker and nginx</h1>
</body>
</html>

Once the container runs, this page will be served at:

http://localhost:80
⚙️ CI/CD Pipeline
GitHub Actions Workflow

.github/workflows/ci.yml

name: Docker CI

on:
  push:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Build Docker Image
        run: docker build -t my-nginx .
What it does:
Triggers on every push
Checks out repository code
Builds Docker image automatically
🚀 How to Run Locally
1. Build Docker image
docker build -t my-nginx .
2. Run container
docker run -p 80:80 my-nginx
3. Open in browser
http://localhost:80
🎯 Learning Outcome

After completing this project, you will understand:

Docker image creation
Serving static websites using Nginx
Basic CI/CD using GitHub Actions
📌 Author

Simple DevOps practice project 🚀
