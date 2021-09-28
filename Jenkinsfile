pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Parallel') {
          steps {
            echo 'Build it'
            sh 'echo build build '
            sh 'pip3 install -r requirements.txt'
          }
        }

        stage('Test') {
          steps {
            sh 'echo test it'
            sh 'python3 manage.py jenkins --enable-coverage'
            junit 'reports/junit.xml'
            echo 'Cobertura'
            cobertura(coberturaReportFile: 'reports/coverage.xml')
          }
        }

      }
    }

  }
}
