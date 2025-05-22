pipeline {
    agent any
	    environment {        DOCKERHUB_CREDENTIALS = credentials('docker')    }
    stages {
        stage('Build') {
            steps {
		     app = docker.build("davidlennuk808/app-prod")
            }
        }
stage('Upload to Dockerhub') {
	steps {
		docker.withRegistry('https://registry.hub.docker.com', 'docker') {
            app.push("davidlennuk808/app-prod")
        }
	
	}
	}
    }
}

