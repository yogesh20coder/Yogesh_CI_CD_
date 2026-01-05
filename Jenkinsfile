pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop cicd-demo || true
                docker rm cicd-demo || true
                docker run -d -p 80:80 --name cicd-demo cicd-demo
                '''
            }
        }
    }
}

