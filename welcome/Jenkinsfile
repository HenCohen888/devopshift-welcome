pipeline {
    agent any

    stages {

        stage('SCM Pull') {
            steps {
                echo 'Pulling source code...'
            }
        }

        stage('Parallel Tests') {
            parallel {

                stage('Bandit Scan') {
                    steps {
                        echo 'Running Bandit scan...'
                        sleep 5
                    }
                }

                stage('Docker Build') {
                    steps {
                        echo 'Building Docker image...'
                        sleep 10
                    }
                }

                stage('Sonarqube Scan') {
                    steps {
                        echo 'Running Sonarqube scan...'
                        sleep 7
                    }
                }

                stage('Trivy Scan') {
                    steps {
                        echo 'Running Trivy scan...'
                        sleep 6
                    }
                }
            }
        }

        stage('Parallel Phase 2') {
            parallel {

                stage('Docker Push') {
                    steps {
                        echo 'Pushing Docker image...'
                        sleep 5
                    }
                }

                stage('Unit Test') {
                    steps {
                        echo 'Running Unit Tests...'
                        sleep 5
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running final tests...'
            }
        }

        stage('End') {
            steps {
                echo 'Pipeline completed successfully!'
            }
        }
    }
}