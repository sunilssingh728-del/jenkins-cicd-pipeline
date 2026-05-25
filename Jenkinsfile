pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/sunilssingh728-del/beginner-html-site-styled.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f html-container || true
                docker run -d -p 8080:80 --name html-container html-site
                '''
            }
        }
    }
}
