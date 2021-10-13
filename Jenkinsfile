pipeline {
  agent any

  stages {
    stage ('Build') {
      steps {
        git 'https://github.com/StefansiTwo/java-rest-api-calculator.git'
        sh './mvnw clean compile'
      }
    }
    stage ('Testing') {
      steps {
        sh './mvnw test'
      }
      post {
        always {
          junit '**/target/surefire-reports/TEST-*.xml'
        }
      }
    }
  }
}
