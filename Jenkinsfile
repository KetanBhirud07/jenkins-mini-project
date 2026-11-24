pipeline {
    agent any

    stages {
        
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 -m pytest test_app.py'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-mini-app .'
            }
        }
    }
}
