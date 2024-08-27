pipeline {
    agent any
  environment {
        GIT_REPO = 'https://github.com/sakhil9495/example-project.git'  // Replace with your repository
        APACHE_DIR = '/var/www/build'  // Apache build directory on the host
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repositoryy
                echo 'Checkout stage this'
                    git branch: 'main', url: "${GIT_REPO}"
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
              script {
                    // Assume the container ID is known or retrieved dynamically
                    def containerId = '4a4d0a561083'
                    
                    // Copy files from Docker container to Jenkins workspace
                    sh "sudo docker cp ${containerId}:/var/jenkins_home/workspace/Demo_Project_main tempfolder"
                    
                    // Move files from Jenkins workspace to Apache directory
                    sh "sudo mv tempfolder/Demo_Project_main/* ${APACHE_DIR}/"
                }
            }
        }
    }
}
