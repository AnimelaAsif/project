node {
    git url: 'https://github.com/AnimelaAsif/project.git'
    def branch = env.BRANCH_NAME

    if (branch == 'master') {
        if (git branch: 'master', diffFilter: 'd', quiet: true) {
            stage('Build and deploy dev') {
                echo"Build to deploy the code for master"
            }
        } else {
            echo "master is idle"
        }
    } else if (branch == 'dev') {
        if (git branch: 'dev', diffFilter: 'd', quiet: true) {
            stage('Build and deploy dev') {
                echo"Build and deploy the code for dev"
            }
        } else {
            echo "dev is idle"
        }
    } else if (branch == 'qa') {
        if (git branch: 'qa', diffFilter: 'd', quiet: true) {
            stage('Build and deploy qa') {
                echo"Build and deploy the code for qa"
            }
        } else {
            echo "qa is idle"
        }
    } else {
        echo "This branch is not configured for deployment"
    }
}
