pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git url: 'https://github.com/sahana22-aug/nodejs-ci-cd-demo.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t sahana-node-app .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'docker stop node-app || true'
                sh 'docker rm node-app || true'
                sh 'docker run -d --name node-app -p 3000:3000 sahana-node-app'
            }
        }
    }
}
