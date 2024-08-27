pipeline {
    agent {
        docker {
            image 'node:18'
            args '-u root' // Run as root user if you need to install additional packages
        }
    }
    
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
                    // Install Node.js dependencies
                    sh 'npm install'
                }
            }
        }

      
        stage('Build') {
            steps {
                // Run build steps
                steps {
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
