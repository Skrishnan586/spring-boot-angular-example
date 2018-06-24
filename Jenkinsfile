pipeline {
  agent any
  stages {
    stage('build backend') {
      parallel {
        stage('build backend') {
          steps {
            sh '''cd ./server/
./mvnw package'''
          }
        }
        stage('build frontend') {
          steps {
            sh '''cd ./client/
npm install 
ng build'''
          }
        }
      }
    }
  }
}