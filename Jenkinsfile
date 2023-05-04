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
                // Get some code from a GitHub repository
                git url: 'https://github.com/wof300/cicd-pipeline.git', branch: 'main'
                // Change file permisson
                sh "chmod +x -R ./scripts"
                // Run shell script
                sh "./scripts/build.sh"
      }
    }

  }
}
