pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: "*/${params.BRANCH}"]], userRemoteConfigs: [[url: 'https://github.com/94davgev/trailrunners.git']]])
            }
        }
        stage('Build and Test Python Project') {
            steps {
                script { 
                    bat 'python -m robot C:\Users\David\Desktop\trailrunners\trailrunners\selenium\labb2.robot'
                }
            }
            post {
                always {
                    robot outputPath: 'C:\Users\David\Desktop\trailrunners\trailrunners\selenium'

                }
            }
        }
    }
}




