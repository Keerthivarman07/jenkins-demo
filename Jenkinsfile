pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/keerthivarman07/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Python application...'
                bat 'python --version'
                bat 'python -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application tests...'
                bat 'python -m unittest -v test_app.py'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline completed successfully!'
        }
        failure {
            echo 'CI Pipeline failed. Check the console output.'
        }
    }
}
