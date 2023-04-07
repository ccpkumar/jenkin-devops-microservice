//SCRIPTED
//node {
	//	echo "Build"
		//echo "Test"
	//	echo "IntegrationTest"
//}

//DECLARATIVE

pipeline {
	agent any
	//This will run the image in docker container
	//agent { docker {image 'maven:3.6.3'}}
	//agent { docker {image 'node:13.8'}}
	environment {
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				//sh 'node --version'
				sh 'docker version'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER = $env.BUILD_NUMBER"
				echo "BUILD_ID = $env.BUILD_ID"
				echo "BUILD_TAG = $env.BUILD_TAG"
				echo "BUILD_URL = $env.BUILD_URL"
				echo "JOB_NAME= $env.JOB_NAME"
				
			}
		}
		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('IntegrationTest') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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
