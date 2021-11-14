//DECLARATIVE

pipeline{
	//agent any
	//agent {docker {image 'maven:3.6.3'}}
	//agent {docker {image 'node:lts-alpine3.14'}}
	stages{
   

		stage("Build"){
			steps{
		//sh 'mvn --version'		
		//sh 'node --version'	
		echo "Build"	
		echo "PATH- $PATH"	
		echo "JOB_NAME- $env.JOB_NAME"	
		echo "EXECUTOR_NUMBER- $env.EXECUTOR_NUMBER"	
		echo "NODE_LABELS- $env.NODE_LABELS"	
		echo "BUILD_TAG- $env.BUILD_TAG"	
		
			}
			
		}

		stage("Test"){
			steps{				
	
		echo "Test"
	
			}
			
		}

		stage("Integration Test"){
			steps{
				
		echo "Integration Test"
			}
			
		}
	}
	post{
		always{
			echo "I am always awasome,"
		}
		success{
			echo "I run when you are success build ,"
		}
		failure{
			echo "I run when you fail,"
		}
	}
}