pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/<your-username>/ci-cd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f cicd-container || true
                docker run -d -p 80:80 --name cicd-container cicd-demo
                '''
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/yogesh20coder/Yogesh_CI_CD_.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f cicd-container || true
                docker run -d -p 80:80 --name cicd-container cicd-demo
                '''
            }
        }
    }
}

