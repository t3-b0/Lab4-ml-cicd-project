pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Train Model') {
            steps {
                script {
                    docker.image('python:3.8').inside {
                        sh 'python train_model.py'
                    }
                }
            }
        }
        stage('Validate Model') {
            steps {
                script {
                    docker.image('python:3.8').inside {
                        sh 'python validate_model.py'
                    }
                }
            }
        }
        stage('Deploy Model') {
            steps {
                script {
                    docker.image('python:3.8').inside {
                        sh 'python deploy_model.py'
                    }
                }
            }
        }
    }
}

