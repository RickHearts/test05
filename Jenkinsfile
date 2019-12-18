pipeline {
  agent any
  stages {
    stage('Browser Tests') {
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

    stage('Edge') {
      steps {
        sleep 5
        echo 'Edge tests'
        input(message: 'do you want to continue', ok: 'continue')
      }
    }

  }
}