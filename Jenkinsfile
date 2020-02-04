pipeline {
  agent {
    docker {
      image 'mven:3.3.9-jdk-8'
    }

  }
  stages {
    stage('Init Stage 1') {
      steps {
        sh '''echo yo dude I am a pipeline bro
echo ok some diagnostics inc
echo PATH =${PATH}
echo ls
mvn clean'''
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