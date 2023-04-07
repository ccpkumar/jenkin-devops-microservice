//SCRIPTED
//node {
	//	echo "Build"
		//echo "Test"
	//	echo "IntegrationTest"
//}

//DECLARATIVE

pipeline {
	//agent any
	//This will run the image in docker container
	//agent { docker {image 'maven:3.6.3'}}
	agent { docker {image 'node:13.8'}}
	stages {
		stage('Build') {
			steps {
				//sh 'mvn --version'
				sh 'node --version'
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('IntegrationTest') {
			steps {
				echo "IntegrationTest"
			}
		}	
	} 
	
	post {
		always {
			echo 'I am awesome . I always run'
		}
		success {
			echo 'I am awesome . I  run when you are successful'
		}
		failure {
			echo 'I  run when you are Fail'
		}
	}
}
