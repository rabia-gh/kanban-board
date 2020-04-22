pipeline {
 agent any
 environment {
     mvnHome = tool name: 'maven', type: 'maven'
     mvnCMD = "${mvnHome}/bin/mvn"
     }
 options {
 skipDefaultCheckout()
 }
 stages {
  stage('SCM') {
   steps {
    checkout scm
   }
  }
  stage('Compile & package') {
        steps {
              sh "cd kanban-app/kanban-app"
              sh "${mvnCMD} clean package"
          }
          }
   stage('Unit Tests') {
    steps {
     sh "cd kanban-app/kanban-app"
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
          
          
