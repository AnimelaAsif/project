pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            when {
                branch 'dev'
            }
            steps {
                echo "its dev"
            }
        }
        stage('QA') {
            when {
                branch 'qa'
            }
            steps {
                echo "its in qa"
            }
        }
    }
}
