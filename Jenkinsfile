// SCRIPTED, Note: you can remove stage part and leave the echo statements
pipeline {
	agent any

	tools {
		maven 'myMaven'
		dockerTool 'myDocker'
	}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	include:
	- remote: https://gitlab.com/gitlab-org/gitlab-foss/-/raw/14-6-stable/lib/gitlab/ci/templates/Jobs/Code-Quality.gitlab-ci.yml

	code_quality:
	variables:
		DOCKER_TLS_CERTDIR: /certs
	stage: verify
	rules:
		- if: $NEXY_CI_STAGE_VERIFY != "1" || $CODE_QUALITY_DISABLED
		when: never
		- if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
		- if: $CI_MERGE_REQUEST_IID

	stages {
		stage ('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"

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
	

