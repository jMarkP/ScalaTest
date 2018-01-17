pipeline {
  agent {
    label 'sbt-slave'
  }

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

    stage('Verification') {
      steps {
        ansiColor('xterm') {
          sh "sbt ';headerCheck ;scalastyle ;sbt:scalafmt::test ;scalafmt::test'"
        }
      }
    }

    stage('Test') {
      steps {
        ansiColor('xterm') {
          sh "sbt scripted"
        }
      }
    }
  }
}