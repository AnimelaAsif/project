pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        stage('branch check'){    
            steps {
                script {
                    def branchName = env.GIT_BRANCH
                    if (branchName == null || branchName == '') {
                        echo "Unable to determine branch name"
                        return
                    }
                    if (branchName.startsWith('origin/dev')) {
                        echo "changes made on dev branch"
                        stage('dev') {
                            echo "steps to exectue in dev"
                        }
                    }
                    else if (branchName.startsWith('origin/qa')) {
                        echo "changes made on dev branch"
                        stage('qa') {
                            echo "steps to exectue in qa"
                        }
                    } 
                    else {
                        echo "cheanges were made on unknown branch: ${branchName}"
                    } 
                }
            }
        }    
    }
}
