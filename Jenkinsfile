pipeline {

	agent any

	stages{

		stage('Build'){

			steps{

				echoi "Build"
				
			}

		}

		stage('Test'){

			steps{

				echo "Test"
		
			}

		}

		stage('integration test'){

			steps{

				echo " Integration Test"
			}

		}
	} 
	
	post {

		always {

			echo " I run always"
		}

		success {

			echo " I run when the build is successful"
		}

		failure {

			echo "I run when build fails"
			emailext body: "Building has failed!", subject: 'FAILURE', to: 'hendwan_fencing@hotmail.com'

		}
	}

}
