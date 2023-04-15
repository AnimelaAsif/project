pipeline {
    agent any
    stages {
        stage('Dev') {
            when {
                branch == "dev"
            }
            steps {
                echo "changes done in Dev"
            }
        }

        stage('QA') {
            when {
                branch == "qa"
            }
            steps {
                echo "changes done in QA"
            }
        }

        stage('master') {
            when {
                branch == "master"
            }
            steps {
                echo "changes done in MASTER"
            }
        }
    }
}
