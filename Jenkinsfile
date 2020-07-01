pipeline {
  agent {
    docker {
      image 'python'
    }

  }
  stages {
    stage('b') {
      steps {
        sh '''pwd
ls'''
      }
    }

    stage('run') {
      steps {
        sh 'python -m py_compile sources/add2vals.py sources/calc.py'
      }
    }

  }
}