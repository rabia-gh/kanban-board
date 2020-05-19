pipeline {
  agent { label 'master' }
  stages {
    stage('Build and Test') {
      parallel {
        stage("Build and Test Linux") {
          stages {
            stage("Build (Linux)") {
              agent any
              steps {
                echo "Inside for loop 1"
              }
            }
            stage("Test (Linux)") {
              agent any
              steps {
                echo "Inside for loop 2"
              }
            }
          }
        }
        stage("Build and Test Windows") {
          stages {
            stage("Build (Windows)") {
              agent any
              steps {
                echo "Inside for loop 3"
              }
            }
            stage("Test (Windows)") {
              agent any
              steps {
                echo "Inside for loop 4"
              }
            }
          }
        }
      }
    }
  }
}
