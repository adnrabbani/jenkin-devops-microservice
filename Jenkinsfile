
pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
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