pipeline {
  // agent { node { label 'local' } }
  agent { docker { image 'python:3.7.2' } }

  stages {
    // stage('setup') {
    //   steps {
    //     sh 'python --version'
    //     // sh 'pyenv local 3.8.0'
    //     sh 'virtualenv .env'
    //     sh 'source .env/bin/activate'
    //     }
    //   }
      stage('build') {
        steps {
          sh 'pip install -r requirements.txt'
        }
      }
      stage('test') {
        steps {
          sh 'python test.py'
        }
      }
    }
  post {
    always {
      junit 'test-reports/*.xml'
    }  
  }
}
