pipeline {
    agent any
    environment {
        IMAGE_NAME = "jeet4949/my-devops-app:v1"
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from GitHub...'
                git branch: 'main', url: 'https://github.com/Jeet4949/devops-project.git'
            }
        }
        
        stage('Build Image') {
            steps {
                script {
                    echo 'Building Docker Image...'
                    sh "docker build -t $IMAGE_NAME ."
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-creds', passwordVariable: 'DOCKER_PASS', usernameVariable: 'DOCKER_USER')]) {
                        sh "echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin"
                        sh "docker push $IMAGE_NAME"
                    }
                }
            }
        }
    }
}
