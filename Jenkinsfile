pipeline {
 agent any
 environment {
     mvnHome = tool name: 'maven', type: 'maven'
     mvnCMD = "${mvnHome}/bin/mvn"
     }
 options {
  //skipDefaultCheckout()
  checkoutToSubdirectory('kanban-app') 
 }
 stages {
  stage('SCM') {
   steps {
    checkout scm
   }
  }
  stage('Compile & package') {
        steps {
          
              sh "${mvnCMD} clean package"
          }
          }
   stage('Unit Tests') {
    steps {
    sh '${mvnCMD} test'
   }
   post {
    always {
     junit 'target/surefire-reports/**/*.xml'
    }
   }
  }
  }
  }
          
          
