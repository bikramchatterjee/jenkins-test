pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/bikramchatterjee/jenkins-test.git'
            }
        }

        stage('Setup Python') {
            steps {
                script {
                    bat 'python3 -m venv venv'
                    bat 'source venv/bin/activate'
                    bat 'pip install -r requirements.txt || true'
                }
            }
        }

        stage('Run Python App') {
            steps {
                bat 'python app.py'
            }
        }
    }
}
