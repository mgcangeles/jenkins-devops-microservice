// SCRIPTED, Note: you can remove stage part and leave the echo statements
pipeline {
	// agent any
	agent {
		 docker { 
				image 'maven:3.9.1'
			} 
		 }
	
	stages {
		stage ('Build') {
			steps {
				sh "mvn --version"
				echo "Build"
			}
		}
		stage ('Test') {
			steps {			
				echo "Test"
			}
		}
		stage ('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	
	post {
		always {
			echo 'Im awesome. I run always'
		}
		success {
			echo 'I run when you are successful'
		}
		failure	 {
			echo 'I run when you fail'
		}
	}
}
	

