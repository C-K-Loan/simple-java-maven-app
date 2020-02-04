pipeline {
  agent {
    docker {
      image 'maven:3.3.9-jdk-8'
    }

  }
  stages {
    stage('Init Stage 1') {
      steps {
        sh '''echo yo dude I am a pipeline bro
echo ok some diagnostics inc
echo ls'''
      }
    }

    stage('Build') {
      steps {
        sh 'mvn install'
      }
    }

    stage('Report Stage') {
      steps {
        junit 'target/surefire-reports/*.xml'
      }
    }

  }
}