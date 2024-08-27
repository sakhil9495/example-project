pipeline {
    agent {
        docker {
            image 'alpine:latest'  // Use a base Alpine image for more control
            args '-v /var/run/docker.sock:/var/run/docker.sock'  // Allow Docker within Docker
        }
    }
    
    stages {
      stage('Install Dependencies') {
            steps {
                script {
                    // Install Node.js and npm
                    sh '''
                    apk update
                    apk add --no-cache nodejs npm
                    npm --version
                    '''
                    // Install Angular CLI globally
                    sh 'npm install -g @angular/cli'
                }
            }
        }
      
        stage('Checkout') {
            steps {
                // Clone the repositoryy
                echo 'Checkout stage this'
                    git branch: 'main', url: 'https://github.com/sakhil9495/example-project.git'
            }
        }
      
        stage('Build') {
            steps {
                // Install project dependencies and build the Angular project
                sh 'npm install'
                sh 'ng build'  // Build the project for production
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
