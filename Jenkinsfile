pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f devops-site || true'
            }
        }

        stage('Remove Old Image') {
            steps {
                sh 'docker rmi devops-website || true'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t devops-website .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name devops-site devops-website'
            }
        }
    }
}
