pipeline {
    agent any

    stages {
        stage ('build') {
            steps {
                bat "mvn compile"
            }
        }
        stage ('test') {
            steps {
                // Kör testerna
                bat "mvn test"
                // Publicera testresultaten från Maven
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Build and Test Python Project') {
            steps {
                script { 
                    bat 'python -m robot C:/Users/David/Desktop/trailrunners/trailrunners/selenium/labb2.robot'
                }
            }
            post {
                always {
                    robot outputpath: 'C:/Users/David/.jenkins/workspace/David_Gevriye_Maraha' , passThreshold: 80.0, unstableThreshold: 70.0, onlyCritical: false
                    
                }
            }
        }
    }
}














