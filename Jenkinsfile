pipeline {
    agent { label "docker" }
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials("Dockerhub-credentials")
    }
    
    stages {
        stage('Build') {
            steps { 
                sh "docker build -t 32322323/javademo ."
            }
        }
        stage('Login') {
            steps {
                sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"
            }
        }
        stage('Push') {
            steps {
                sh "docker push 32322323/javademo:latest"
            }
        }
    }
}