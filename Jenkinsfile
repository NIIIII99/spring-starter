pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        bat 'mvnw.cmd clean package'
      }
    }
  }
}