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

			echo " Testing...."
		}

		success {

			echo " I run when the build is successful"
		}

		failure {

			echo "I run when build fails"
			emailext body: 'dfdfdfdfdfd', subject: 'Failure', to: 'hendwanabozide@gmail.com'

		}
	}

}
