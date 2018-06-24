pipeline {
  agent any
  stages {
    stage('build backend') {
      steps {
        sh '''cd ./backend/
./mvnw package'''
      }
    }
  }
}