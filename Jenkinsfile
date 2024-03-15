pipeline {
    agent any

    stages {
        
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




