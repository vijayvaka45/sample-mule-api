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
				script {
                    if (env.BRANCH_NAME == 'dev') {
						bat 'mvn deploy -DmuleDeploy -Denv=Dev -DconnectedApp.clientId=febd36b1cd054c908553db292f77fccf -DconnectedApp.clientSecret=99B5864a87E94189B026F9f00B9A5669 -DconnectedApp.grantType=client_credentials'
                    }
					else if (env.BRANCH_NAME == 'test') {
						bat 'mvn clean deploy -DmuleDeploy -Denv=Test -DconnectedApp.clientId=1ca626cacb5b4865b6123d8513328d4d -DconnectedApp.clientSecret=1073e6a2B55947939B75B7338D52B1f0 -DconnectedApp.grantType=client_credentials'
                    }
					else {
                        echo 'Sorry You can not deploy'
                    }
                    }
                
				
            }
        }
    }
}