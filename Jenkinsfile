pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                deleteDir() // Optional: Clear workspace
                git branch: 'main', url: 'https://github.com/mia-amanda/Simple_Calculator.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Use 'bat' for Windows environment
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                echo 'Running calculator script...'
                bat 'python calculator.py 1 10 20'  // Passes the operation and numbers as arguments
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'pytest --maxfail=1 --disable-warnings'
            }
        }
    }

    post {
        success {
            echo 'Build and test stages completed successfully.'
        }
        failure {
            echo 'One or more stages failed. Check the logs for details.'
        }
    }
}
