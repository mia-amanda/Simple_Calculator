pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR-USERNAME/YOUR-REPO.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install required dependencies listed in requirements.txt
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                // This stage simulates the "build" step
                echo 'Running calculator script...'
                sh 'python calculator.py'
            }
        }

        stage('Test') {
            steps {
                // Run the unit tests using pytest
                echo 'Running unit tests...'
                sh 'pytest --maxfail=1 --disable-warnings'
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
