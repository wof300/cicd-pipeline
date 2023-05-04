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
          git url: 'https://github.com/wof300/cicd-pipeline.git'
          sh './scripts/build.sh'
        }

      }
    }

  }
}