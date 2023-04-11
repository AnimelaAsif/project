pipeline {
    agent any
    parameters {
        gitBranch(name: 'branch', type: 'string', defaultValue: 'dev', description: 'Branch to build')
    }
    stages {
        stage('Build') {
            when {
                expression {
                    params.branch == 'dev'
                }
            }
            steps {
                echo "is dev"
            }
        }
        stage('QA') {
            when {
                expression {
                    params.branch == 'qa'
                }
            }
            steps {
                echo "qa"
            }
        }
    }
}
