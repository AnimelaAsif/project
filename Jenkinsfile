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
                    if (branchName.startsWith('origin/dev')) {
                        echo "Changes were made on the dev branch"
                        stage('dev') {
                            echo "changes made on dev branch"
                        }
                    } else if (branchName.startsWith('origin/qa')) {
                        echo "Changes were made on the qa branch"
                        stage('qa') {
                            echo "changes made on qa branch"
                        }
                    } else {
                        echo "Changes were made on an unknown branch: ${branchName}"
                    }
                }
            }
        }
    }
}
