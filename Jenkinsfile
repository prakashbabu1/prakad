pipeline {
	agent any
	
	stages{
		stage('Build'){
			steps{
				sh 'ant -f build.xml -v'
			}
		}
		stage('Test'){
			steps{
				sh 'echo "Hello Guyzz"'
			}
		}
		stage('deploy'){
			steps{
				sh 'sudo cp /home/ec2-user/.jenkins/war/WEB-INF/lib/*.jar /mnt/'	
				}
			}
	}
	post{
		success{
			archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
	}
}
