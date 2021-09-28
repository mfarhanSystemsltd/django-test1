pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo Edited Placeholder.'
            sh 'echo Build it'
          }
        }

        stage('Test') {
          steps {
            sh 'echo test it '
          }
        }

      }
    }

  }
}