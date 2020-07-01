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

    stage('test') {
      agent {
        docker {
          image 'grihabor/pytest'
        }

      }
      steps {
        sh 'pytest --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
      }
    }

  }
}