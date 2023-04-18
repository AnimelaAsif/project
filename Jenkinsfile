pipeline {
  agent any
  stages {
    stage('Print Branch Name') {
      steps {
        script {
          def branchName = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
          println "The changes were made in branch: ${branchName}"
        }
      }
    }
  }
}
