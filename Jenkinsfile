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
      
        stage('Build Angular Project') {
            steps {
                script {
                    // Use Docker to run Node.js and Angular CLI
                    docker.image('node:18-alpine').inside {
                        // Install Angular CLI globally
                        sh 'npm install -g @angular/cli'
                        // Install project dependencies and build the Angular project
                        sh 'npm install'
                        sh 'ng build'
                    }
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
