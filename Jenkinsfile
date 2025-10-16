pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sagartikare/devops_project.git', credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92'
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

