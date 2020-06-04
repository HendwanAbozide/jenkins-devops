pipeline {


	agent any

	// agent {
		
	// 	docker {
	// 		image 'node:12.17'

	// 	}

	// }

	environment {

	
		dockerhome= tool 'mydocker3'
		nodehome = tool 'mynode3'
		PATH ='$dockerhome/bin:$nodehome/bin:$PATH'
	}

	stages{

		stage('Build'){

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
			mail bcc: '', body: 'gfgfgfgfgfgf', cc: '', from: '', replyTo: '', subject: 'Failure', to: 'hendwanabozide@gmail.com'

		}
	}

}
