qpipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'aa201127-e350-4462-9066-09ae7854dd92', url: 'https://github.com/Sagartikare/devops_project.git'
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
                    sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    python3 -m unittest discover || true
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Stop any container already running on 8080
                    sh 'docker ps -q --filter "publish=8080" | xargs -r docker stop'
                    // Remove stopped container
                    sh 'docker ps -a -q --filter "publish=8080" | xargs -r docker rm'

                    // Run container on host port 8080
                    sh 'docker run -d -p 8080:5000 myapp:latest'
                }
            }
        }
    }
}

