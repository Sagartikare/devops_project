pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sagartikare/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t myapp:latest .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'python3 -m pip install -r requirements.txt'
                    sh 'python3 -m unittest discover'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -d -p 8080:8080 myapp:latest'
                }
            }
        }
    }
}
