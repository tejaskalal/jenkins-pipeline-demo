pipeline {
  agent any

  environment {
    APP_NAME = "demo-app"
  }

  stages {

    stage('Checkout') {
      steps {
        echo "Checking out code from GitHub"
        checkout scm
      }
    }

    stage('Build') {
      steps {
        echo "Building the app ${APP_NAME}"
        sh '''
          echo "Simulating build process..."
          sleep 2
        '''
      }
    }

    stage('Test') {
      steps {
        echo "Running tests for ${APP_NAME}"
        sh '''
          echo "Simulating test process..."
          sleep 2
        '''
      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      steps {
        echo "Deploying ${APP_NAME} "
        sh '''
          echo "Deployment successful!"                      
        '''
      }
    }
  }
  
  post {
      success {
        echo "Pipeline completed successfully!"
      }
      failure {
        echo "Pipeline failed."
      }
      always {
        echo "Pipeline execution finished."
      }
    }
}
