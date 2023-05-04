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
          // Get some code from a GitHub repository
          git url: 'https://github.com/wof300/cicd-pipeline.git', branch: 'main'
          // Change file permission
          sh "chmod +x -R ./scripts"
          // Run build script
          sh "./scripts/build.sh"
       }
     }
   }
     stage('Tests') {
            steps {
                nodejs('19.7.0') {
                // Run test script
                sh './scripts/test.sh'
        }
      }
    }
      stage('Docker Image Build') {
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
}

