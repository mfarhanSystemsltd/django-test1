pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build the repo'
          }
        }

        stage('Test') {
          steps {
            echo 'Test the repo'
          }
        }

      }
    }

  }
}