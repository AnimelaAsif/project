pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        stage('Check Branch') {
            steps {
                script {
                    def branchName = env.GIT_BRANCH
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
