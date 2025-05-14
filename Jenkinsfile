pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }
    
    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage('Unit Test') {
            steps {
                script {
                    // Run unit tests
                    for (int i = 0; i < 60; i++) {
                        echo "Running unit test iteration ${i + 1}"
                    }
                    // Use the Maven wrapper to run the tests
                }
                sh "mvn test"
            }
        }
    }
}