pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "${env.GIT_BRANCH}"
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    // Verify Docker is available
                    sh 'docker --version'
                    // Verify Docker Compose is available
                    sh 'docker-compose --version'
                    // Run Docker Compose build
                    sh 'docker-compose build'
                }
            }
        }
    }
}

