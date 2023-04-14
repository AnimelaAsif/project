pipeline {
    agent any
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
    stages {
        stage('Dev') {
            when {
                branch 'dev'
            }
            steps {
                echo "changes seen in dev branch"
            }
        }
    }
}
