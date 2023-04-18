pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/master']],
                          doGenerateSubmoduleConfigurations: false,
                          extensions: [[$class: 'RelativeTargetDirectory',
                                        relativeTargetDir: 'project']],
                          submoduleCfg: [],
                          userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        stage('Print branch') {
            steps {
                script {
                    def branchName = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    echo "Changes were made on branch ${branchName}"
                }
            }
        }
    }
}
