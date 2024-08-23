pipeline {
    agent any
    
    stages {
        stage("Checkout") {
            steps {
                // Clone the repository
              echo "checkout stage"
            }
        }
        
        stage("Build") {
            steps {
                // Run build steps
              echo "Build stage"
                }
            }
        }
        
        stage("Test") {
            steps {
                // Run unit tests
            }
        }

        stage("Deploy") {
            steps {
                // Deploy application
                echo "deploy stage"
            }
        }
    }
}
