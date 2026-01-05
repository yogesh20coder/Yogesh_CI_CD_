pipeline{
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                // Pointing to your specific repo
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
