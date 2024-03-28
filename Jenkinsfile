pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'python -m pip install tk'
            }
        }
        stage('Test') {
            steps {
                sh 'python main5.py' // Replace your_script_name.py with the actual filename of your Tkinter script
            }
        }
    }
}
