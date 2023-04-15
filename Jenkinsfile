pipeline {
    agent any
    stages {
        stage('Dev') {
            when {
                branch== "dev"
            }
            steps {
                echo "changes done in Dev"
            }
        }

        stage('QA') {
            when {
                not { branch== "dev" }
                branch== "qa"
            }
            steps {
                echo "changes done in QA"
            }
        }

        stage('master') {
            when {
                not { branch== "dev" }
                not { branch== "qa" }
                branch== "master"
            }
            steps {
                echo "changes done in MASTER"
            }
        }
    }
}
