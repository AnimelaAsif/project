pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/dev']], userRemoteConfigs: [[url: 'https://github.com/AnimelaAsif/project.git']]])
            }
        }
        
        stage('Build and Test') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo "dev"
            }
        }
    }
}
