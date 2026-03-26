pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/priya1198/mini-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 5000:5000 myapp
                '''
            }
        }
    }
}

