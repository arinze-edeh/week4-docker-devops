pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo "Simulating build step"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Simulating test step"'
            }
        }

        stage('Validation') {
            steps {
                echo 'Running validation checks...'
                sh '''
                    echo "Checking for required files"
                    test -f Jenkinsfile && echo "Jenkinsfile found"
                    test -f docker-compose.yml && echo "docker-compose.yml found"
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the console output above for details.'
        }
    }
}