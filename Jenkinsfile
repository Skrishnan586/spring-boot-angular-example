pipeline {
  agent any
  stages {
    stage('build backend') {
      steps {
        sh '''cd ./server/
./mvnw package'''
      }
    }
  }
}