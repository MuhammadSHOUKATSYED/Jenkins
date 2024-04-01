pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Replace this with your build command, if needed
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                // For example:
                // sh 'npm run deploy'
            }
        }
    }

    post {
        success {
            echo 'The Node.js backend build was successful!'
            // You can trigger further actions on success, like deployment
        }

        failure {
            echo 'The Node.js backend build failed!'
            // You can take actions in case of failure, like notifying the team
        }
    }
}
