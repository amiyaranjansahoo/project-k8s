pipeline {
	agent any
	tools {
		
		maven 'm3'
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
		
		stage('Push to docker hub') {
			steps {
				withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerpwd')]) {
					sh "docker login -u amiyaranjansahoo -p ${dockerpwd}"
					sh "docker push amiyaranjansahoo/dockerimg:v7"
				}
			}
		}
		
		
	}

}
