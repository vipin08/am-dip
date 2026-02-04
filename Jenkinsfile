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

        stage('Run Container') {
            steps {
                bat 'docker rm -f am-dip-container || exit 0'
                bat 'docker run -d -p 5000:5000 --name am-dip-container am-dip-app'
            }
        }
    }
}
