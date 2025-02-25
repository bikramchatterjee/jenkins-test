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
                    sh 'python3 -m venv venv'
                    sh 'source venv/bin/activate'
                    sh 'pip install -r requirements.txt || true'
                }
            }
        }

        stage('Run Python App') {
            steps {
                sh 'python app.py'
            }
        }
    }
}
