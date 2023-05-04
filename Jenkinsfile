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
        // Use Node.js commands
        withNodeJS(nodeJSInstallationName: 'node') {
          // Get some code from a GitHub repository
          git url: 'https://github.com/wof300/cicd-pipeline.git', branch: 'main'
          // Change file permission
          sh "chmod +x -R ./scripts"
          // Install dependencies
          sh "npm install"
          // Run shell script
          sh "./scripts/build.sh"
        }
      }
    }
  }
}
