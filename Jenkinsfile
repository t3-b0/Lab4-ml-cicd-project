pipeline {
    agent {
        docker {
            image 'python:3.8' // Puedes usar cualquier versión de Python que necesites
        }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Train Model') {
            steps {
                sh 'python train_model.py'
            }
        }
        stage('Validate Model') {
            steps {
                sh 'python validate_model.py'
            }
        }
        stage('Deploy Model') {
            steps {
                sh 'python deploy_model.py'
            }
        }
    }
}
