pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          checkout scm
          sh "ls -ltr"
        }

      }
    }

    stage('Application Build') {
      steps {
        nodejs('19.7.0') {
          git(url: 'https://github.com/wof300/cicd-pipeline.git', branch: 'main')
          sh 'chmod +x -R ./scripts'
          sh './scripts/build.sh'
        }

      }
    }

    stage('Tests') {
      steps {
        nodejs('19.7.0') {
          sh './scripts/test.sh'
        }

      }
    }

    stage('Docker Image Build') {
      agent any
      environment {
        registry = 'wof300/cicdrepo'
      }
      steps {
        script {
          def customImage = docker.build("${registry}:${env.BUILD_ID}")
        }

      }
    }

    stage('Docker Image Push') {
      steps {
        script {
          docker.withRegistry('', 'dockerhub-id') {
            docker.image("${registry}:${env.BUILD_ID}").push('cicd_pipeline')
          }
        }

      }
    }

  }
  environment {
    registry = 'wof300/cicdrepo'
  }
}