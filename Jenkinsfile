pipeline {
  agent any
  environment {
    DIRECTORY_PATH = 'C:\Users\Stewie\OneDrive\Documents\Deakin_Uni\T1_Assignment\SIT223\6.1P\'
    TESTING_ENVIRONMENT = 'testing'
    PRODUCTION_ENVIRONMENT = 'Stewie'
  }
  stages {
    stage('Build') {
      steps {
        checkout scm
        echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
        echo 'Compile the code and generate any necessary artefacts'
      }
    }

    stage('Test') {
      steps {
        echo 'Unit tests'
        echo 'Integration tests'
      }
    }

    stage('Code Quality Check') {
      steps {
        echo 'Check the quality of the code'
      }
    }

    stage('Deploy') {
      steps {
        echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
      }
    }

    stage('Approval') {
      steps {
        echo 'Simulating manual approval (sleeping for 10 seconds)'
        sleep time: 10
      }
    }

    stage('Deploy to Production') {
      steps {
        echo "Deploying the application to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
      }
    }
  }

  post {
    always {
      cleanWs()
    }
  }
}
