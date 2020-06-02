
pipeline {

	agent any

    try{


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

					echo " Integration Test"

				}

			}
		} 
	} catch (err){


		emailext body: "Caught : ${err}", subject: 'first pipeline', to: 'Hendwan_fencing@hotmail.com'

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
		}
	}

}
