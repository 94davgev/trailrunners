pipeline {
    agent any

    stages {
        stage ('build'){
            steps {
                bat "mvn compile"
            }
        }
        stage ('test') {
            steps {
                // Kör testerna
                bat "mvn test"
                // Publicera testresultaten
                junit 'target/surefire-reports/*.xml' // Ange sökvägen till dina testresultatfiler
            }
        }
    }
}








