pipeline {
  //agent { label 'linux' }
  agent any
  tools {
    maven 'Maven 3'}
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/CDarnielle/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clear compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefile-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
