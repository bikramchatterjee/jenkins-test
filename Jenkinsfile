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
                    bat 'python -m venv venv'
                    bat 'venv\\Scripts\\activate'
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
