pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub') // Jenkins credentials ID
        DOCKER_IMAGE = 'dockernikunj22/react_django_demo_app'
    }

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repo...'
                // git 'https://github.com/your/repo.git'  // Optional if not using multibranch
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // sh 'npm test' or pytest etc.
            }
        }

        stage('Login to DockerHub') {
            steps {
                echo 'Logging into DockerHub...'
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }

        stage('Push to DockerHub') {
            steps {
                echo 'Pushing Docker image to DockerHub...'
                sh 'docker push $DOCKER_IMAGE'
            }
        }
    }
}
