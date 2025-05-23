
pipeline{
	agent any
	//agent{ docker{ image 'maven:3.6.3'} }
	//agent{ docker{ image 'node:24-alpine3.20'} }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$mavenHome/bin:$dockerHome/bin:$PATH"
	}

	stages{
		stage('Checkout'){
			steps{
				sh 'docker --version'
				sh 'mvn --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.BUILD_TAG"
				echo "BUILD URL - $env.BUILD_URL"
				

			}
		}
		stage('Compile'){
			steps{
				sh 'mvn clean compile'
			}
		}

		stage('Test'){
			steps{
				sh 'mvn test'
				echo "Test"
			}
		}
		stage('Integration'){
			steps{
				sh 'mvn failsafe:integration-test failsafe:verify'
				echo "Int Test"
			}
		}
	}
	post{
		always{
			echo "always run"
		}
		success{
			echo "pass"
		}
		failure{
			echo "fail"
		}
	}
}