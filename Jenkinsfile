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
                
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'npm run deploy'
            }
        }
    }

    post {
        success {
            echo 'The Node.js backend build was successful!'
        }

        failure {
            echo 'The Node.js backend build failed!'
        }
    }
}
