pipeline {
    agent any
    
    stages {
        stage('Install Node.js and npm') {
             steps {
                script {
                    sh '''
                    # Install Node.js and npm if not present
                    if ! command -v node &> /dev/null; then
                        curl -sL https://deb.nodesource.com/setup_18.x | bash -
                        apt-get install -y nodejs
                    fi
                    
                    # Install Angular CLI globally
                    if ! command -v ng &> /dev/null; then
                        npm install -g @angular/cli
                    fi
                    '''
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
