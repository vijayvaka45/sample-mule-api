pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
				steps {
					bat 'mvn deploy -DmuleDeploy -Denv=Dev -DconnectedApp.clientId=febd36b1cd054c908553db292f77fccf -DconnectedApp.clientSecret=99B5864a87E94189B026F9f00B9A5669 -DconnectedApp.grantType=client_credentials'
				}
			}
    }
}
