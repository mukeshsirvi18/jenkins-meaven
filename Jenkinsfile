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
        
        stage('Run Application') {
            steps {
                // Run the Java application
                sh 'java -cp target/jenkins-meaven-1.0-SNAPSHOT.jar com.example.App'
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

