pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build the repo'
            sh 'echo Another Placeholder.'
          }
        }

        stage('Test') {
          steps {
            echo 'Test the repo'
            echo 'Test it again'
            sh '''sleep 5
'''
            sh 'echo Success!'
          }
        }

      }
    }

  }
}