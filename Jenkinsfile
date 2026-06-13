pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Source code available'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook deploy.yml'
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful'
        }

        failure {
            echo 'Deployment Failed'
        }
    }
}
