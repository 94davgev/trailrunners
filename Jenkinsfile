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
                    // Arkivera XML-testresultaten från Robot Framework-testerna
                    archiveArtifacts artifacts: 'C:/Users/David/Desktop/trailrunners/trailrunners/selenium/output.xml', onlyIfSuccessful: true
                    // Publicera HTML-rapporten från Robot Framework-testerna
                    publishHTML([
                        allowMissing: false,
                        alwaysLinkToLastBuild: true,
                        keepAll: true,
                        reportDir: 'C:/Users/David/Desktop/trailrunners/trailrunners/selenium/logs',
                        reportFiles: 'log.html',
                        reportName: 'Robot Framework Test Log'
                    ])
                    // Publicera HTML-rapporten från Robot Framework-testerna
                    publishHTML([
                        allowMissing: false,
                        alwaysLinkToLastBuild: true,
                        keepAll: true,
                        reportDir: 'C:/Users/David/Desktop/trailrunners/trailrunners/selenium/reports',
                        reportFiles: 'report.html',
                        reportName: 'Robot Framework Test Report'
                    ])
                }
            }
        }
    }
}














