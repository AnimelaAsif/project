pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        stage('Check Branch') {
            steps {
                script {
                    def branchName = env.BRANCH_NAME
                    if (branchName == null || branchName == '') {
                        echo "Unable to determine branch name"
                        return
                    }
                    echo "Changes were made on branch ${branchName}"
                }
            }
        }
    }
}
