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
                branch== "origin/dev"
            }
            steps {
                echo "Changes were made in Dev"
            }
        }
        
        stage('QA') {
            when {
                branch/= "origin/dev"
                branch== "origin/qa"
            }
            steps {
                echo "Changes were made in QA"
            }
        }

        stage('master') {
            when {
                branch/= "origin/dev"
                branch/= "origin/qa"
                branch== "origin/master"
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
