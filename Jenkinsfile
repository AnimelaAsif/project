pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Dev') {
            when {
                changeset "origin/dev"
            }
            steps {
                echo "Changes were made in Dev"
            }
        }
        
        stage('QA') {
            when {
                not { changeset "origin/dev" }
                changeset "origin/qa"
            }
            steps {
                echo "Changes were made in QA"
            }
        }

        stage('master') {
            when {
                not { changeset "origin/dev" }
                not { changeset "origin/qa" }
                changeset "origin/master"
            }
            steps {
                script {
                    sh 'git branch'
                    echo "Changes were made in Master"
                }
            }
        }
    }
}
