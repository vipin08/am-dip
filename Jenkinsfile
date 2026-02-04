pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/vipin08/am-dip.git'
            }
        }

        stage('Build Docker Image') {
    steps {
        bat 'docker build -t am-dip-app .'
    }
}


        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }
    }
}
