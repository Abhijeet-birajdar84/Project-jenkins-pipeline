pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Check Python') {
            steps {
                echo 'Checking Python version...'
                bat 'python --version'
            }
        }

        stage('Install Requirements') {
            steps {
                echo 'Installing dependencies from requirements.txt...'
                bat 'python -m pip install --upgrade pip'
                bat 'python -m pip install -r requirements.txt'
            }
        }

        stage('Test Application') {
            steps {
                echo 'Testing Flask app...'
                bat 'python -c "import app; print(\'App imported successfully\')"'
            }
        }

        stage('Build Complete') {
            steps {
                echo 'Build completed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Jenkins Pipeline Finished: SUCCESS ✅'
        }
        failure {
            echo 'Jenkins Pipeline Finished: FAILURE ❌'
        }
    }
}
