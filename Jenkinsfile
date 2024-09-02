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
        
        stage('Run Application') {
            steps {
                // Run the Java application and display output
                sh 'java -cp target/jenkins-meaven-1.0-SNAPSHOT.jar com.example.App'
            }
        }
    }
    
    post {
        success {
            echo 'Build, Test, and Run Completed Successfully!'
        }
        failure {
            echo 'Build, Test, or Run Failed!'
        }
    }
}

