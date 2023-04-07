//SCRIPTED
//node {
	//	echo "Build"
		//echo "Test"
	//	echo "IntegrationTest"
//}

//DECLARATIVE

pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
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
