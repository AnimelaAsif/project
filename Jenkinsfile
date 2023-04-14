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
            }
            steps {
                echo "checges done in dev branch"
            }
        }
    }
}
