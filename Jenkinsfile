pipeline {
    agent any

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
