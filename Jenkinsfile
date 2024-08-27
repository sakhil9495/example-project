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
                    // Run commands inside a Docker container with Node.js
                    sh '''
                    docker run --rm \
                        -v $(pwd):/usr/src/app \
                        -w /usr/src/app \
                        node:18-alpine sh -c "
                        npm install -g @angular/cli &&
                        npm install &&
                        ng build --prod
                        "
                    '''
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
