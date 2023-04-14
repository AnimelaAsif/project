pipeline {
    agent any
    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'test', 'prod'],
            description: 'Select the environment to deploy to'
        )
    }
    stages {
        stage('Dev') {
            when {
                expression { params.ENVIRONMENT == 'dev' }
            }
            steps {
                echo "you r in dev"
            }
        }
        stage('qa') {
            when {
                expression { params.ENVIRONMENT == 'qa' }
            }
            steps {
                echo "you r in qa"
            }
        }
        stage('Prod') {
            when {
                expression { params.ENVIRONMENT == 'prod' }
            }
            steps {
                echo "you r in prod"
            }
        }
    }
}
