pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          checkout scm
        }

      }
    }

    stage('Application Build') {
      steps {
        script {
          sh 'chmod +x scripts/build.sh'
          sh './scripts/build.sh'
        }

      }
    }

  }
}