DevOps Flask CI/CD Project

## Project Overview
This project demonstrates a basic DevOps workflow by deploying a Python Flask application using Docker on an AWS EC2 instance. The project shows how to build, containerize, and deploy an application in the cloud using common DevOps tools.

## Technologies Used
- Python (Flask)
- Docker
- Git
- AWS EC2
- Linux (Ubuntu)
Project Architecture
Local Development → GitHub Repository → AWS EC2 Server → Docker Container → Running Web Application

## Project Structure devops-flask-cicd
devops-flask-cicd
│
├── app.py
├── Dockerfile
├── requirements.txt
├── Jenkinsfile
├── README.md
│
└── .github
└── workflows
└── deploy.yml


Project Architecture

Developer pushes code to GitHub  
↓  
Jenkins pipeline triggers automatically  
↓  
Docker image is built  
↓  
Old container is stopped and removed  
↓  
New container is deployed on AWS EC2  

Steps Implemented

### 1. Created Flask Application
Developed a simple Python Flask application.

### 2. Containerization
Created a Dockerfile to containerize the Flask application using Docker.

### 3. Version Control
Pushed the project code to GitHub repository for version control.

### 4. Cloud Deployment
Created an EC2 instance on AWS and connected via SSH.

### 5. Docker Setup
Installed Docker on the EC2 Ubuntu server.

### 6. Application Deployment
Pulled the project from GitHub and built the Docker image.

### 7. Container Execution
Ran the container exposing port 5000 to serve the Flask application.

### 8. Application Access
Accessed the deployed application via EC2 public IP.
Example:
http://EC2_PUBLIC_IP:5000

## Commands Used

Clone repository

git clone https://github.com/Ml1727/devops-flask-cicd.git

Build Docker image

docker build -t flask-devops .

Run Docker container

docker run -d -p 5000:5000 flask-devops

Check running containers

docker ps

Application

Simple Flask web application.

app.py


from flask import Flask

app = Flask(name)

@app.route('/')
def home():
return "Hello DevOps! CI/CD Pipeline Running Successfully"

if name == 'main':
app.run(host='0.0.0.0', port=5000)


---

# Docker Setup

Dockerfile


FROM python:3.9

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python", "app.py"]


---

# Jenkins Pipeline

The Jenkins pipeline performs the following tasks:

1. Pull code from GitHub
2. Build Docker image
3. Stop existing container
4. Remove old container
5. Deploy new container

Jenkinsfile


pipeline {
agent any

stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t flask-devops .'
        }
    }

    stage('Run Docker Container') {
        steps {
            sh 'docker stop flask-container || true'
            sh 'docker rm flask-container || true'
            sh 'docker run -d -p 5000:5000 --name flask-container flask-devops'
        }
    }

}

}


---
How to Run Locally

Clone repository


git clone https://github.com/yourusername/devops-flask-cicd.git


Navigate to project


cd devops-flask-cicd


Build Docker image


docker build -t flask-devops .


Run container


docker run -d -p 5000:5000 flask-devops


Open browser


http://localhost:5000

 Deployment

Application is deployed on **AWS EC2** using Jenkins.

After pipeline execution:


docker ps


Example output:


CONTAINER ID IMAGE PORTS NAMES
be2a3cdbd8ad flask-devops 0.0.0.0:5000->5000/tcp flask-container


Access application


http://EC2-PUBLIC-IP:5000

http://EC2-PUBLIC-IP:5000


---

# CI/CD Workflow

1. Developer commits code
2. Code pushed to GitHub
3. Jenkins detects changes
4. Jenkins builds Docker image
5. Docker container deployed automatically
6. Application becomes available on EC2 server

---

# Future Improvements

- Push Docker image to DockerHub
- Deploy application to Kubernetes
- Add monitoring using Prometheus and Grafana
- Add automated testing stage in Jenkins pipeline

---

# Author

DevOps CI/CD Project  
Built for learning **real-world DevOps workflows**
Updated Final Project Structure

Your project should look like this:

devops-flask-cicd
│
├── app.py
├── Dockerfile
├── requirements.txt
├── Jenkinsfile
├── README.md
│
└── .github
    └── workflows
        └── deploy.yml
What Recruiters See From This Project

This project proves you know:

CI/CD pipelines

Containerization

Cloud deployment

DevOps automation

Tools demonstrated:

Jenkins

Docker

GitHub

Amazon Web Services

This is a solid beginner DevOps portfolio project.

If you want, I can also show you the next project that makes recruiters very impressed:

“Production DevOps Pipeline with Jenkins + DockerHub + Kubernetes + Monitoring”

That project can make your resume look like a real DevOps engineer. 🚀


## Key DevOps Concepts Demonstrated
- Infrastructure deployment on AWS
- Containerization using Docker
- Git-based version control
- Remote server management via SSH
- Application deployment in cloud environment

 Future Improvements
- Implement CI/CD using GitHub Actions
- Deploy using Kubernetes
- Automate infrastructure using Terraform


