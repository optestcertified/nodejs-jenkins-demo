pipeline {
    agent any

    tools {
        nodejs "node17"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/nodejs-jenkins-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Build step – for Node.js, this is usually npm test or lint'
            }
        }

        stage('Deploy') {
            steps {
                sh 'nohup node server.js > output.log 2>&1 &'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
