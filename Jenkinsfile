pipeline {

	// agent any

	agent {
		
		docker {
			image 'node:12.17'

		}

	}

	stages{

		try{

			stage('Build'){

				steps{
					sh 'node --version'
					echo "Build"
					
				}

			}

			stagie('Test'){

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

		catch(all) {
            currentBuild.result='FAILURE'
			emailext body: 'Build failed', subject: 'Failure', to: 'www.hendwanabozide@gmail.com'

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
			emailext body: 'Build failed', subject: 'Failure', to: 'www.hendwanabozide@gmail.com'

		}
	}

}


