pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build it'
            sh 'echo build build '
            sh 'pip install -r requirements.txt'
          }
        }

        stage('Test') {
          steps {
            sh 'echo test it'
            sh 'python3 manage.py jenkins --enable-coverage'
            junit 'reports/junit.xml'
          }
        }

      }
    }

  }
}