pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the GitHub repository
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Clean and package the Maven project
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests (optional)
                sh 'mvn test'
            }
        }
    }
    
    post {
        success {
            echo 'Build and Test Completed Successfully!'
        }
        failure {
            echo 'Build or Test Failed!'
        }
    }
}

