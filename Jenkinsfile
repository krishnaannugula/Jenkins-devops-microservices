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
				
		sh "mvn failsafe:integration-test failsafe:verify"
			}
			
		}
		stage("Package"){
			steps{
				
		sh "mvn package -DskipTests"
			}
			
		}
		stage("Doker_Build"){
			steps{
				//DECLARATIVE

				"docker build -t annugulakrishna/currency-exchange-devops:$env.BUILD_TAG"
				
				//or as below

				//Scripted
				
				script{
					dockerImage = docke.build("annugulakrishna/currency-exchange-devops:${env.BUILD_TAG}")
				
				}			
		
			}
			
		}
		stage("Docker_Push"){
			steps{
				
		script{
				docker.withRegistry('','DockerhubCred'){

				dockerImage.push();
				dockerImage.push('latest')
					}

				}
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