pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'first jenkins pipeline'
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://54.89.168.144:9000 \\
  -Dsonar.login=sqp_c3e3630b5b097e2a9e2940cfb795239b2437d58d'''
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }

  }
}