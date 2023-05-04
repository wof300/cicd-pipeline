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
     environment {
        PATH = "$PATH:/usr/local/bin"
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
