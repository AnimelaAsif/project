pipeline {
  agent any
  stages {
    stage('Print branch name') {
      steps {
        echo "The current branch is ${env.BRANCH_NAME}"
      }
    }
    stage('Perform action based on branch name') {
      when {
        expression { env.BRANCH_NAME == 'origin/master' }
      }
      steps {
        echo "Performing action for master branch"
      }
    }
    stage('Perform another action based on branch name') {
      when {
        anyOf {
          expression { env.BRANCH_NAME == 'origin/dev' }
        }
      }
      steps {
        echo "Performing action for dev or qa branch"
      }
    }
  }
}
