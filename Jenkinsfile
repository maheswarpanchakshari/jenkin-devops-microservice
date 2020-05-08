// Scripte pipeline
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }


// Declarative pipeline
pipeline{
    //  agent {docker { image 'maven:3.6.3'}}
	    agent any
		 environment {
			 dockerHome = tool 'myDocker'
			 mavenHome= tool 'myMaven'
			 PATH="$dockerHome/bin:$mavenHome/bin:$PATH"

		 }
	    stages {
			stage('Checkout'){
				steps{
				    sh 'mvn --version'
				    // sh 'docker version'
					echo "maven version is"
					echo "Build"
				}
			}

			stage('Compile'){
				steps{
					sh "mvn clean compile"
				}
			}
				stage('Test'){
				steps{
					sh "mnv test"
					echo "Test"
				}
			}
				stage('Integration test'){
				steps{
					sh "mvn failsafe:integration-test failsafe:verify"
					echo "Integration test"
				}
			}
		}
		
		post {
			always {
				echo "i will execute always"
			}
			success {
				echo "i run when you are successfull"
			}
			failure {
				echo "i run when you will fail"
			}
		}
}