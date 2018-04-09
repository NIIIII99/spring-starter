pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        bat 'mvnw clean package'
      }
    }
  }
}