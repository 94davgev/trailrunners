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
                bat "mvn test" // Kör testerna
            }
        }
    }
}




