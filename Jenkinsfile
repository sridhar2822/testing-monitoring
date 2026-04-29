pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop devops-app || true'
                sh 'docker rm devops-app || true'
                sh 'docker run -d -p 3001:3001 --name devops-app devops-app'
            }
        }
    }
}
