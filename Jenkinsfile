pipeline {
    agent any

    stages {

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
      

