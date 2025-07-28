pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repo...'
            }
        }

        stage('Build') {
            steps {
                echo 'Running build steps...'
                // sh 'npm install' or python setup steps
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // sh 'npm test' or pytest
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // sh './deploy.sh' or custom command
            }
        }
    }
}
