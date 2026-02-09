pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/nisargthakkar59/ecommerce-ci-cd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ecommerce-react-app .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                docker stop ecommerce || true
                docker rm ecommerce || true
                docker run -d --name ecommerce -p 8080:80 ecommerce-react-app
                '''
            }
        }
    }
}

