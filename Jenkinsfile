pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repositoryy
                echo 'Checkout stage this'
                dir('example-project') {
                    git branch: 'main', url: 'https://github.com/sakhil9495/example-project.git'
                }
            }
        }
        
        stage('Build') {
            steps {
                // Run build steps
                echo 'Build stage'
            }
        }
        
        stage('Test') {
            steps {
                // Run unit tests
                echo 'Test stage'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy application
                echo 'Deploy stage'
            }
        }
    }
}
