pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repositoryy
                echo 'Checkout stage this'
                    git branch: 'main', url: 'https://github.com/sakhil9495/example-project.git'
            }
        }
      
      stage('Install Dependencies') {
            steps {
                script {
                    // Install Angular CLI
                    sh 'npm install'
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    // Install Angular CLI
                    sh 'ng build'
                }
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
