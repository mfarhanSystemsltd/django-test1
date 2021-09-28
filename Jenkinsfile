pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo Edited Placeholder.'
            sh 'echo Build it'
            archiveArtifacts(artifacts: 'reports/junit.xml', fingerprint: true)
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