pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build . -t davidlennuk808/app-prod'
            }
        }
stage('Upload to Dockerhub') {
	steps {
		
			 sh "docker login"
	    sh 'docker push davidlennuk808/app-prod'
	
	}
	}
    }
}

