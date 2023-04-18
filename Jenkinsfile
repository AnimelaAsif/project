pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: "${env.BRANCH_NAME}"]],
                          doGenerateSubmoduleConfigurations: false,
                          extensions: [[$class: 'RelativeTargetDirectory',
                                        relativeTargetDir: 'project']],
                          submoduleCfg: [],
                          userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        stage('Dev') {
            when {
                changeset "origin/dev"
            }
            steps {
                echo "changes done in Dev"
            }
        }
        
        stage('QA') {
            when {
                not { changeset "origin/dev" }
                changeset "origin/qa"
            }
            steps {
                echo "changes done in QA"
            }
        }

        stage('master') {
            when {
                not { changeset "origin/dev" }
                not { changeset "origin/qa" }
                changeset "origin/master"
            }
            steps {
                echo "changes done in MASTER"
            }
        }
    }
}
