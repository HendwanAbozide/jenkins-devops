pipeline {

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

		stage('integration test'){

			steps{

				echoi " Integration Test"
			}

		}
	} 
	
	post {

		always {

			echo " Testing...."
		}

		success {

			echo " I run when the build is successful"
		}

		failure {

			echo "I run when build fails"
			emailext body: 'Build failed', subject: 'Failure', to: 'www.hendwan_fencing@hotmail.com'

		}
	}

}
