pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Setup Python') {
            steps {
                echo 'Checking Python...'
                bat '"C:\\Users\\WINDOWS\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing pytest...'
                bat '"C:\\Users\\WINDOWS\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" -m pip install pytest'
            }
        }

        stage('Run Unit Tests') {
            steps {
                echo 'Running unit tests...'
                bat '"C:\\Users\\WINDOWS\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" -m pytest test_calculator.py -v'
            }
        }
    }

    post {
        success {
            echo 'All tests passed successfully!'
        }
        failure {
            echo 'Some tests failed!'
        }
    }
}
