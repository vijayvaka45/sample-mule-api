pipeline {
    agent any
    parameters {
        string(defaultValue: 'master', description: 'branch', name: 'GIT_BRANCH')
    }
    
    stages {
        stage('Clone sources') {
            steps {
                git branch: "${params.GIT_BRANCH}", url: 'https://github.com/ktoso/maven-git-commit-id-plugin.git'
            }
        }
        
        stage('Build printenv'){
            steps {
                sh 'printenv'
            }
        }
    }
}
