pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app:${GIT_COMMIT} .'
            }
        }

        stage('Test Docker Image') {
            steps {
                sh 'docker run --rm python-app:${GIT_COMMIT} python -m pytest'
            }
        }
    }
}