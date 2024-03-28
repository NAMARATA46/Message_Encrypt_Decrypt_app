pipeline {
    agent {
        label 'python'
    }
    
    stages {
        stage('Setup') {
            steps {
                script {
                    // Create and activate a virtual environment
                    bat 'python -m venv venv' // Using 'bat' instead of 'sh' for Windows
                    bat 'venv\\Scripts\\activate' // Activating virtual environment on Windows
                    // Upgrade pip and install dependencies
                    bat 'python -m pip install --upgrade pip' // Using 'bat' instead of 'sh' for Windows
                    bat 'python -m pip install -r requirements.txt' // Using 'bat' instead of 'sh' for Windows
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    try {
                        // Run tests
                        bat 'python main5.py' // Using 'bat' instead of 'sh' for Windows
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        throw e
                    }
                }
            }
        }
    }
    
    post {
        always {
            // Deactivate virtual environment
            bat 'venv\\Scripts\\deactivate' // Deactivating virtual environment on Windows
        }
        
        success {
            // Post-build actions for success
            echo 'Build and tests passed successfully!'
        }
        
        failure {
            // Post-build actions for failure
            echo 'Build or tests failed!'
        }
    }
}

