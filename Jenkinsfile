pipeline {
    agent any
    stages {
        stage('Dev') {
            when {
                changeset "dev"
            }
            steps {
                echo "changes done in Dev"
            }
        }

        stage('QA') {
            when {
                not { changeset "dev" }
                changeset "qa"
            }
            steps {
                echo "changes done in QA"
            }
        }

        stage('master') {
            when {
                not { changeset "dev" }
                not { changeset "qa" }
                changeset "master"
            }
            steps {
                echo "changes done in MASTER"
            }
        }
    }
}
