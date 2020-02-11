pipeline {
  agent {
    docker {
        image 'python:3.7.2'
    }
  }
  stages {
    stage('build') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }
    stage('Test') {
        steps {
            sh 'py.test tests/test_catalog.py --junitxml=reports/out_report.xml'
        }
        post {
            always {
                junit 'reports/out_report.xml'
            }
        }
    }
  }
}
