pipeline {


	// agent any

	agent {
		
		docker {
			image 'maven:3.6.3'
			// image 'node:12.17'

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

				// sh 'node --version'
				// sh 'docker --version'
				sh 'mvn --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.BUILD_TAG"

			}

		}

		stage('Compile'){

			steps{

				sh 'mvn clean compile'  //like npm install
		
			}

		}


		stage('Test'){

			steps{

				sh 'mvn test'
		
			}

		}

		stage('integration test'){

			steps{

				sh "mvn failsafe:integration-test failsafe:verify"
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
