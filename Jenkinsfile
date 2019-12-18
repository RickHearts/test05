pipeline {
  agent any
  stages {
    stage('Chrome') {
      parallel {
        stage('Chrome') {
          steps {
            echo 'chrome tests'
          }
        }

        stage('Firefox') {
          steps {
            echo 'Firefox message'
          }
        }

      }
    }

  }
}