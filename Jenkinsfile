//DECLARATIVE

pipeline{
	agent any
	stages{
		stage("Build"){
			steps{
				
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