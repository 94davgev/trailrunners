pipeline {
    agent any

    parameters {
        choice(name: 'BRANCH', choices: ['main', 'b1'], description: 'Select branch to build')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/94davgev/trailrunners.git']]])
                }
            }
        }
        stage('Build and Test') {
            steps {
                script {
                    
                    sh 'mvn clean test' 
                }
            }
        }
    }
}


