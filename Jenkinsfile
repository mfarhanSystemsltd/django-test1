pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo Edited Placeholder.'
            sh 'echo Build it'
            sh ' pip3 install -r requirements.txt'
            archiveArtifacts 'reports/junit.xml'
          }
        }

        stage('Test') {
          steps {
            sh 'echo test it '
            sh 'python3 manage.py jenkins --enable-coverage'
          }
        }

      }
    }

  }
}