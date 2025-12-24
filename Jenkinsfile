pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/vDevopsvinod/devops-ci-cd-pro.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-ci-cd-pro:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name devops-app-jenkins devops-ci-cd-pro:v1 || true'
            }
        }
    }
}

