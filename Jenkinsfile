pipeline {
	agent {
		node {
			label 'master'
		}
	}
	
	options{
		timestamps()
	}
	
	
	stages{
		stage("Checkout, Test") {
			steps{
				checkout scm
				
				script{
					bat(/mvn clean  test /)
				}
				
			}
		}
		
		stage("Email"){
			steps{
				emailext (to: 'abhinavlanka179@gmail.com', replyTo: 'abhinavlanka179@gmail.com', subject: "Email Report", body: readFile("test-output/index.html"), mimeType: 'text/html');
			}
		}
	}
	

}
