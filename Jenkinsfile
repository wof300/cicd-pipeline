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
    environment {
        PATH = "$PATH:/usr/local/bin"
    }
      steps {
        script {
          sh 'cd scripts && chmod +x build.sh && ./build.sh'
        }

      }
    }

  }
}
