pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('docker')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    app = docker.build("davidlennuk808/app-prod")
                }
            }
        }
        stage('Upload to Dockerhub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker') {
                        app.push("latest")
                    }
                }
            }
        }
    }
}


