pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout(
                    [
                        $class: 'GitSCM',
                        branches: [[name: '*/dev']],
                        doGenerateSubmoduleConfigurations: false,
                        extensions: [],
                        submoduleCfg: [],
                        userRemoteConfigs: [[
                            url: 'https://github.com/AnimelaAsif/project.git'
                        ]]
                    ]
                )
            }
        }
        stage('Dev') {
            when {
                branch 'dev'
                script {
                    println("Branch name: ${env.BRANCH_NAME}")
                    println("When condition: ${env.when}")
                }
            }
            steps {
                echo "changes done in dev branch"
            }
        }
    }
}
