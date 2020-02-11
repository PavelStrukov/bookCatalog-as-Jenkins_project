pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {
    stage('build') {
      steps {
        sh 'python3 -m virtualenv venv'
        sh 'source venv/bin/activate'
        sh 'pip3 install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'pytest tests/test_catalog.py'
      }
    }
  }
}
