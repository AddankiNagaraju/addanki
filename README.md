pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/your-username/your-repo.git'
        BRANCH_NAME = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${BRANCH_NAME}", url: "${GIT_REPO}"
            }
        }

        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
    }
}
