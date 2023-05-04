pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          git branch: 'main', credentialsId: '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', url: 'https://github.com/wof300/cicd-pipeline.git'

        }

      }
    }

  }
}
