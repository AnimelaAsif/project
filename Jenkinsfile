pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/dev']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'CleanCheckout']],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]
                ])
            }
        }
        
        stage('Build and Test') {
            when {
                changeset "*/dev"
            }
            steps {
                echo "changes made in dev branch"
            }
        }
    }
}
