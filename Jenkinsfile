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
                    def branches = currentBuild.changeSets.collect { it.branches }.flatten().unique()
                    return branches.size() == 1 && branches[0].name == 'dev'
                }
            }
            steps {
                echo "dev"
            }
        }
    }
}
