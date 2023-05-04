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
          sh 'curl https://github.com/wof300/cicd-pipeline/main/scripts/build.sh | bash'
        }

      }
    }

  }
}