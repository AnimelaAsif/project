pipeline {
    agent any
    stages {
        stage('Dev') {
            when {
                branch 'dev' 
            }
            steps {
                echo "you r in dev"
            }
        }
    }
    options {
        checkoutToSCM {
            git {
                remote {
                    url 'https://github.com/AnimelaAsif/project.git'
                }
                branch 'dev'
            }
        }
    }
}
