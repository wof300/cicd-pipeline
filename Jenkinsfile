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
       steps {
                dir('scripts') {
                    sh 'chmod +x build.sh'
                    sh './build.sh'
        }

      }
    }

  }
}
