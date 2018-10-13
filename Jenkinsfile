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
				sh 'sudo cp /root/.jenkins/workspace/pipeline_l/lib/*.jar /opt/'	
				}
			}
	}
	post{
		success{
			archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
	}
}
