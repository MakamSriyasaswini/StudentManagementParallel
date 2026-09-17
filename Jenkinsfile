pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/MakamSriyasaswini/StudentManagementParallel.git'
            }
        }

        stage('Parallel Checks') {
            parallel {

                stage('Frontend Check') {
                    steps {
                        bat '"C:\\Users\\makam\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" frontend_check.py'
                    }
                }

                stage('Backend Check') {
                    steps {
                        bat '"C:\\Users\\makam\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" backend_check.py'
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
