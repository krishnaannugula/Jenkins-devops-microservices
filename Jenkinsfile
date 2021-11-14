//DECLARATIVE

pipeline{
	//agent any
	agent {docker {image 'maven:3.6.3'}}
	stages{

 		stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
   		}

		stage("Build"){
			steps{
		sh 'mvn --version'		
		echo "Build"	
		
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