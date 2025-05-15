/***** BRANCH - TEST *****/
pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }
    
    stages {
        stage('Maven Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -DskipTests=true"
                archiveArtifacts 'target/my-java-app-*.jar'
            }
        }
        stage('Unit Test') {
            steps {
                sh "mvn test"
                junit(testResults:'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
            }
        }
        stage('Local Deployment') {
            steps {
                sh """ java -jar target/my-java-app-*.jar > /dev/null & """
            }
        }
        stage('Integration Test') {
            steps {
                sh 'sleep 5s'
            }
        }
    }
}