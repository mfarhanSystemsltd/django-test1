pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
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
            cobertura(coberturaReportFile: 'cobertura/coverage.xml', classCoverageTargets: 'cobertura autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: \'reports/coverage.xml\', conditionalCoverageTargets: \'70, 0, 0\', failUnhealthy: false, failUnstable: false, lineCoverageTargets: \'80, 0, 0\', maxNumberOfBuilds: 0, methodCoverageTargets: \'80, 0, 0\', onlyStable: false, sourceEncoding: \'ASCII\', zoomCoverageChart: false')
          }
        }

      }
    }

  }
}