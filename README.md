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
│
├── app.py
├── Dockerfile
├── requirements.txt
├── README.md
│
├── .github
│   └── workflows
│       └── deploy.yml

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


