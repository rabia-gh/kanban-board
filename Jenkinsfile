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
  stage('acess folder') {
        steps {
              sh """
                cd kanban-app
                pwd 
              """
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
          
          
