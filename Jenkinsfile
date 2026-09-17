pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/YOUR_USERNAME/jenkins-project-3.git'
            }
        }
        stage('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        sh 'python3 frontend_check.py'
                    }
                }
                stage('Backend Check') {
                    steps {
                        sh 'python3 backend_check.py'
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