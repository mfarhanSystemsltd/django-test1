pipeline {
    agent any 
    environment {
        DISABLE_AUTH = 'true'
    }
    stages {
        stage('Clean workspace'){
            steps{
                cleanWs();
            }
        }
         stage('Git checkout') { 
            steps {
              sh "echo ${env.DISABLE_AUTH}"
              git branch: 'mfarhanSystemsltd-patch-1', url: 'https://github.com/mfarhanSystemsltd/django-test1.git'
            }
        }
         stage('Install requirements') { 
            steps {
                // sh 'apt install python3-pip'
                sh 'pip3 install -r requirements.txt' 
            }
        }
         stage('Run and generate coverage test') { 
            steps {
                
                sh 'coverage run manage.py'
               sh 'coverage xml'
                // sh ' python3 manage.py jenkins --enable-coverage --source=.'
            }
        }
//          stage('View coverage report') { 
//             steps {
//             junit 'reports/junit.xml'
//             }
//         }
        //  stage('Plot graph') { 
        //      steps {
        //      cobertura autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: 'reports/coverage.xml', conditionalCoverageTargets: '70, 0, 0', failUnhealthy: false, failUnstable: false, lineCoverageTargets: '80, 0, 0', maxNumberOfBuilds: 0, methodCoverageTargets: '80, 0, 0', onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false
        //     }
        //  }
         stage ("Extract test results") {
             steps{
               cobertura autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: 'coverage.xml', conditionalCoverageTargets: '100, 0, 17', failUnhealthy: false, failUnstable: true, fileCoverageTargets: '100, 0, 0', lineCoverageTargets: '100, 0, 0', maxNumberOfBuilds: 0, methodCoverageTargets: '100, 0, 0', onlyStable: false, packageCoverageTargets: '100, 0, 0', sourceEncoding: 'ASCII', zoomCoverageChart: false
             }
        }
    }
}
