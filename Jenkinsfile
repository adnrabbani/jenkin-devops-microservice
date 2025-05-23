
pipeline{
	//agent any
	//agent{ docker{ image 'maven:3.6.3'} }
	agent{ docker{ image 'node:24-alpine3.20'} }

	stages{
		stage('Build'){
			steps{
				sh 'node --version'
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration'){
			steps{
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