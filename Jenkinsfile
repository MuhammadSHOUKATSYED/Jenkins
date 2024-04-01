pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/NaseemKhan005/react-bank-app'
            }
        }
        
        stage('Dependency Installation') {
            steps {
                // You might need different commands depending on your project setup
                sh 'npm install express' // For frontend dependencies
                // Add backend dependency installation commands here
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build' // Assuming this is your React build script
            }
        }
        
        stage('Test') {
            steps {
                // Add your test execution commands here
                // For example, if you're using Jest for React testing:
                sh 'npm test'
            }
        }
        
        stage('Containerized') {
            steps {
                // Build Docker images for frontend and backend (if applicable)
                script {
                    docker.build('frontend-image', '.')
                    // Add commands to build backend image if needed
                }
                // Run Docker Compose to deploy the containers
                sh 'docker-compose up -d'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
            // You can add additional steps here for failure handling
        }
    }
}
