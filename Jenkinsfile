pipeline {

  agent any

  environment {
    // Ensure that build scripts recognise the environment they are running within
    CI = 'jenkins'
  }

  stages {
    stage('Compile') {
      steps {
        sh "sbt ';clean ;compile ;doc'"
      }
    }
  }
}