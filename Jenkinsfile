//DECLARATIVE

pipeline{
	agent any
	//agent {docker {image 'maven:3.6.3'}}
	//agent {docker {image 'node:lts-alpine3.14'}}
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}


	stages{
   

		stage("Checkout"){
			steps{
		sh 'mvn --version'		
		sh 'docker version'	
		echo "Build"	
		echo "PATH- $PATH"	
		echo "JOB_NAME- $env.JOB_NAME"	
		echo "EXECUTOR_NUMBER- $env.EXECUTOR_NUMBER"	
		echo "NODE_LABELS- $env.NODE_LABELS"	
		echo "BUILD_TAG- $env.BUILD_TAG"	
		
			}
			
		}

		stage("Complie"){
			steps{				
	
		sh "mvn clean compile"
	
			}
			
		}
		stage("Test"){
			steps{				
	
		sh "mvn test"
	
			}
			
		}

		stage("Integration Test"){
			steps{
				
		echo "mvn failsafe:integration-test failsafe:verify"
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