pipeline {
    agent any

    environment {
        APP_NAME = 'welcome-app'
        ENVIRONMENT = 'dev'
        VERSION = '1.0.0'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
                echo "Environment is ${ENVIRONMENT}"
                echo "Version is ${VERSION}"
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'my-creds',
                    usernameVariable: 'USERNAME',
                    passwordVariable: 'PASSWORD'
                )]) {
                    echo "Deploying with username: ${USERNAME}"
                    echo "Deploying with password: ${PASSWORD}"
                }
            }
        }
    }
}