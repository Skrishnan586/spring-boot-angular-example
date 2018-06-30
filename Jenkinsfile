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
    stage('build docker') {
      steps {
        sh 'docker-compose up -d --build '
      }
    }
    stage('archive') {
      steps {
        archiveArtifacts 'server/target/*.jar'
        archiveArtifacts 'client/dist/*'
      }
    }
    stage('test') {
      steps {
        sh '''curl http://localhost:9000
curl http://localhost:4002
sleep 30'''
      }
    }
    stage('down docker container') {
      steps {
        sh 'docker-compose down'
      }
    }
  }
}