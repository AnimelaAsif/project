pipeline {
  agent any
  
  stages {
    stage('Git Checkout') {
      steps {
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/master']],
                  doGenerateSubmoduleConfigurations: false,
                  extensions: [[$class: 'CloneOption', depth: 0, noTags: true, reference: '', shallow: true]],
                  submoduleCfg: [],
                  userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
      }
    }
    
    stage('Check for changes') {
      steps {
        script {
          def branches = sh(returnStdout: true, script: 'git branch -r | grep -v \'\\^ \\*\\$\'').trim().split('\\n')
          for (branch in branches) {
            sh("git checkout -f ${branch}")
            def changes = sh(returnStdout: true, script: 'git fetch origin ${branch} && git diff remotes/origin/${branch}').trim()
            if (changes) {
              echo "Changes made in branch: ${branch}"
            }
          }
        }
      }
    }
  }
}
