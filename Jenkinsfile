
pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv .venv
                    . .venv/bin/activate
                    pip install -r requirements.txt
                    pip install pytest
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    . .venv/bin/activate
                    pytest -v test_app.py
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-mini-app .'
            }
        }
    }
}
