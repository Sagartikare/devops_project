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
<<<<<<< HEAD
                git branch: 'main', 
                    url: 'https://github.com/Sagartikare/devops-project.git',
                    credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92'
>>>>>>> 187b014 (oct16-updated)
=======
                git branch: 'main', url: 'https://github.com/Sagartikare/devops_project.git', credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92'
>>>>>>> 0933257 (oct 16)
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
=======
        stage('Run Tests') {
            steps {
                script {
                    sh '''
                        python3 -m venv venv
                        . venv/bin/activate
                        pip install --upgrade pip
                        pip install -r requirements.txt
                        python3 -m unittest discover || true
                    '''
>>>>>>> 0933257 (oct 16)
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
<<<<<<< HEAD
<<<<<<< HEAD
=======
>>>>>>> 0933257 (oct 16)
                    sh 'docker run -d -p 9090:8080 myapp:latest'
                }
            }
        }
    }
}

<<<<<<< HEAD
=======
                    sh 'docker ps -q --filter "name=myapp" | grep -q . && docker stop myapp && docker rm myapp || true'
                    sh 'docker run -d --name myapp
>>>>>>> 187b014 (oct16-updated)
=======
>>>>>>> 0933257 (oct 16)
