pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/vDevopsvinod/devops-ci-cd-pro.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-ci-cd-pro:jenkins .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f devops-app || true
                docker run -d -p 8080:80 --name devops-app devops-ci-cd-pro:jenkins
                '''
            }
        }
    }
}

