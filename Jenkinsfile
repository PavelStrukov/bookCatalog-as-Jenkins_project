pipeline {
  agent {
    docker {
        image 'python:3.7.2'
        image 'qnib/pytest'
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
            sh 'py.test --verbose --junit-xml test-reports/results.xml tests/test_catalog.py'
        }
        post {
            always {
                junit 'test-reports/results.xml'
            }
        }
    }
  }
}
