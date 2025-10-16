pipeline {
    agent any
<<<<<<< HEAD
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sagartikare/devops_project.git', credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92'
=======

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/Sagartikare/devops-project.git',
                    credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92'
>>>>>>> 187b014 (oct16-updated)
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t myapp:latest .'
                }
            }
        }

<<<<<<< HEAD
        stage('Run Tests') {
            steps {
                script {
                    sh 'python3 -m pip install -r requirements.txt'
                    sh 'python3 -m unittest discover'
=======
        stage('Install Dependencies & Run Tests') {
            steps {
                script {
                    sh 'pip3 install -r requirements.txt || true'
                    sh 'python3 -m unittest discover || true'
>>>>>>> 187b014 (oct16-updated)
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
<<<<<<< HEAD
                    sh 'docker run -d -p 8080:8080 myapp:latest'
                }
            }
        }
    }
}

=======
                    sh 'docker ps -q --filter "name=myapp" | grep -q . && docker stop myapp && docker rm myapp || true'
                    sh 'docker run -d --name myapp
>>>>>>> 187b014 (oct16-updated)
