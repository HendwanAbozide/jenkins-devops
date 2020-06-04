pipeline {


	// agent any

	agent {
		
		docker {
			image 'node:12.17'

		}

	}

	// environment {

	
	// 	dockerhome= tool 'mydocker3'
	// 	nodehome = tool 'mynode3'
	// 	PATH ='$dockerhome/bin:$nodehome/bin:$PATH'
	// }

	stages{

		stage('Checkout'){

			steps{

				sh 'node --version'
				// sh 'docker --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.BUILD_TAG"

			}

		}

		// stage('Compile'){

		// 	steps{

		// 		sh 'node clean compile'
		
		// 	}

		// }


		stage('Test'){

			steps{

				sh 'node test'
		
			}

		}

		stage('integration test'){

			steps{

				sh "node failsafe:integration-test failsafe:verify"
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
			mail bcc: '', body: 'gfgfgfgfgfgf', cc: '', from: '', replyTo: '', subject: 'Failure', to: 'hendwanabozide@gmail.com'

		}
	}

}
