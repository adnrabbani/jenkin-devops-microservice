#node {
#		echo "Build"
#		echo "Test"
#		echo "Integration Test"
#}

pipeline{
	agent any
	stage{
		stage('Build'){
			steps{
				echo "Build"
			}
		}
	}
	stage{
		stage('Test'){
			steps{
				echo "Test"
			}
		}
	}
	stage{
		stage('Integration'){
			steps{
				echo "Int Test"
			}
		}
	}
}