pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm ci'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodejs-demo-app:jenkins .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker rm -f nodejs-jenkins-app || true
                    docker run -d -p 3001:3000 --name nodejs-jenkins-app nodejs-demo-app:jenkins
                '''
            }
        }
    }
}