pipeline {

  environment {
    // Ensure that build scripts recognise the environment they are running within
    CI = 'jenkins'
  }

  stages {
    stage('Compile') {
      steps {
        ansiColor('xterm') {
          sh "sbt ';clean ;compile ;doc'"
        }
      }
    }
  }
}