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
          nodejs('20.1.0') {
          // Get some code from a GitHub repository
          git url: 'https://github.com/wof300/cicd-pipeline.git', branch: 'main'
          // Change file permission
          sh "chmod +x -R ./scripts"
          // Run shell script
          sh "./scripts/build.sh"
        }
      }
    }
  }
}
