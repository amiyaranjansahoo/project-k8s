pipeline {
	agent any
	tools {
		
		maven 'mvn3'
	}
	stages {
		stage('Maven Build') {
			steps {
				sh 'mvn clean package'
			}
		}
		
		stage('Docker Build image') {
			steps {
				sh "docker build . -t amiyaranjansahoo/dockerimg:v7 "
			}
		}
		
	}

}
