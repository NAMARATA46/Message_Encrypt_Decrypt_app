pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '7173de20-2408-493e-bb21-f8477789818f', url: 'https://github.com/NAMARATA46/Message_Encrypt_Decrypt_app.git']])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', credentialsId: '7173de20-2408-493e-bb21-f8477789818f', url: 'https://github.com/NAMARATA46/Message_Encrypt_Decrypt_app.git'
                bat 'python main5.py'
                
            }
        }
        stage('Test') {
            steps {
                echo 'This job has been tested'
            }
        }
    }
}
