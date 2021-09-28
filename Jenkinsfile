pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo Edited Placeholder.'
            sh 'echo Build it'
            sh 'echo pip3 install -r requirements.txt'
          }
        }

        stage('Test') {
          steps {
            sh 'echo test it '
            sh 'echo python3 manage.py jenkins --enable-coverage'
          }
        }

        stage('pytest') {
          steps {
            archiveArtifacts(artifacts: 'reports/junit.xml', fingerprint: true)
          }
        }

      }
    }

  }
}