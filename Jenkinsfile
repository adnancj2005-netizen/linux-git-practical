
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building website'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing website files'
                sh 'test -f index.html'
                echo 'Website test passed'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying website to Nginx'
                sh 'cp index.html /usr/share/nginx/html/index.html'
            }
        }

        stage('Verify') {
            steps {
                echo 'Deployment completed'
                sh 'curl -f http://localhost'
            }
        }
    }
}
