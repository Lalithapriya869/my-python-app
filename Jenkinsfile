pipeline {
    agent any

    environment {
        PYTHON = "C:\\Users\\LalithaPriya\\AppData\\Local\\Programs\\Python\\Python311\\python.exe"
    }

    stages {

        stage('Clone Code') {
            steps {
                echo 'Cloning from GitHub...'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '"%PYTHON%" -m pip install --upgrade pip'
                bat '"%PYTHON%" -m pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat '"%PYTHON%" -m pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Running Python app...'
                bat '"%PYTHON%" app.py'
            }
        }
    }

    post {
        success {
            echo '✅ SUCCESS: Pipeline executed correctly!'
        }
        failure {
            echo '❌ ERROR: Check console output!'
        }
    }
}
