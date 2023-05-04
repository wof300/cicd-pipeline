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
          sh 'cd scripts && chmod +x build.sh && ./build.sh'
        }

      }
    }

  }
}