pipeline {
    agent any
    parameters {
        gitParameter(name: 'branch', type: 'string', defaultValue: 'master', description: 'Branch to build')
    }
    stages {
        stage('Build') {
            when {
                expression {
                    params.branch == 'dev'
                }
            }
            steps {
                echo "you r in dev"
            }
        }
        stage('QA') {
            when {
                expression {
                    params.branch == 'qa'
                }
            }
            steps {
                echo "you r in qa"
            }
        }
    }
}
