pipeline {
    agent any
    stages {
        stage('Dev') {
            when {
                changeset "origin/dev"
            }
            steps {
                echo "changes done in Dev"
            }
        }
        
        stage('QA') {
            when {
                not { changeset "origin/dev" }
                changeset "origin/qa"
            }
            steps {
                echo "changes done in QA"
            }
        }

        stage('master') {
            when {
                not { changeset "origin/dev" }
                not { changeset "origin/qa" }
                changeset "origin/master"
            }
            steps {
                echo "changes done in MASTER"
            }
        }
    }
}
