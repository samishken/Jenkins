/***** BRANCH - MAN *****/
pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/my-java-app-*.jar'
      }
    }

    stage('Unit Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }
    stage('Containerization') {
      steps {
        sh 'echo Docker Build Image'
        sh 'echo Docker Tag Image'
        sh 'echo Docker Push Image'
      }
    }
    stage('Kubernetes Deployment') {
      steps {
        sh 'echo Deploy to Kubernetes using ArgoCD'
      }
    }
    stage('Integration Test') {
      steps {
        sh "sleep ${params.SLEEP_TIME}"
        sh 'echo Testing using cURL commands.....'
      }
    }

  }
  tools {
    maven 'M398'
  }
}