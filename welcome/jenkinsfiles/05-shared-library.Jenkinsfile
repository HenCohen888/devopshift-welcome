@Library('my-shared-library') _

pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                script {
                    myLibrary.buildApp()
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    myLibrary.deployApp()
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    myLibrary.cleanup()
                }
            }
        }
    }
}