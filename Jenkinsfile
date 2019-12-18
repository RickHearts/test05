pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Build & Test') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'sh mvn -Dmaven.test.failure.ignore clean package'
        stash(name: 'build-test-artifacts', includes: '**/target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

    stage('Report & Publish') {
      parallel {
        stage('Report & Publish') {
          agent {
            node {
              label 'docker'
            }

          }
          steps {
            unstash 'build-test-artifacts'
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts(onlyIfSuccessful: true, artifacts: 'target/*.jar')
          }
        }

        stage('Publishing') {
          agent {
            node {
              label 'docker'
            }

          }
          steps {
            echo 'working'
          }
        }

      }
    }

  }
}