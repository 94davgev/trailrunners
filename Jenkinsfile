pipeline {
    agent any

    parameters {
        choice(name: 'BRANCH', choices: ['main', 'b1'], description: 'Select branch to build')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: "*/${params.BRANCH}"]], userRemoteConfigs: [[url: 'https://github.com/94davgev/trailrunners.git']]])
                }
            }
        }
        stage('Build and Test Java Project') {
            when {
                expression { params.BRANCH == 'main' || params.BRANCH == 'b1' }
            }
            steps {
                dir('trailrunner') {
                    script {
                        sh 'mvn clean test' // Maven-kommando för att bygga och köra tester för Java-projektet
                    }
                }
            }
        }
        stage('Build and Test Python Project') {
            when {
                expression { params.BRANCH == 'main' || params.BRANCH == 'b1' }
            }
            steps {
                dir('selenium') {
                    script {
                        sh 'python -m unittest discover' // Kommando för att köra Python-tester
                    }
                }
            }
        }
    }
}




