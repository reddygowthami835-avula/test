
pipeline {
    agent any

    tools {
        nodejs 'NodeJS-22'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading React code from GitHub'
                checkout scm
            }
        }

        stage('Check Node and NPM') {
            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing React dependencies'
                sh 'npm ci'
            }
        }

        stage('Build React Application') {
            steps {
                echo 'Building React application'
                sh 'npm run wrong-command'
            }
        }

        stage('Verify Build') {
            steps {
                echo 'Checking production build files'
                sh 'test -f dist/index.html'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: React application built successfully!'
        }

        failure {
            echo 'FAILURE: Please check the Jenkins console output.'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}
