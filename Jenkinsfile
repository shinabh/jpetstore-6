pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'first jenkins pipeline'
        sh './mvnw clean complie'
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw test'
      }
    }

  }
}