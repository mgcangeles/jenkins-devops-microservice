// SCRIPTED, Note: you can remove stage part and leave the echo statements
pipeline {
	agent any
	stages {
		stage ('Build') {
			steps {
				// sh 'mvn --version'
				// sh 'node --version'
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
	

