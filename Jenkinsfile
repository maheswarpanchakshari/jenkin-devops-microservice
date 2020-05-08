// Scripte pipeline
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }


// Declarative pipeline
pipeline{
     agent {docker { image 'maven:3.6.3'}}
	    stages {
			stage('Build'){
				steps{
					echo "maven version is"
					sh 'mvn --version'
					echo "Build"
				}
			}
				stage('Test'){
				steps{
					echo "Test"
				}
			}
				stage('Integration test'){
				steps{
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