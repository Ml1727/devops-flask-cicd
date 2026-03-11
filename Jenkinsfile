pipeline {
    agent any

    stages {

        stage('Clone Repository') {
    steps {
        git branch: 'main', url: 'https://github.com/Ml1727/devops-flask-cicd.git'
    }
}
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-devops .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop flask-container || true'
                sh 'docker rm flask-container || true'
                sh 'docker run -d -p 5000:5000 --name flask-container flask-devops'
            }
        }

    }
}