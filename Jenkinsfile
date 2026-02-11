pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/YogeshS-Mca/devops-project.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop devops-app || true
                docker rm devops-app || true
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:80 --name devops-app devops-app'
            }
        }
    }
}
1~y
pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/YogeshS-Mca/devops-project.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop devops-app || true
                docker rm devops-app || true
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:80 --name devops-app devops-app'
            }
        }
    }
}
