pipeline {
    agent {
        docker {
            image 'docker:20.10.7' // Using a Docker image that includes Docker
            args '-v /var/run/docker.sock:/var/run/docker.sock -v $(pwd):/workspace'
        }
    }

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker --version' // Verify Docker is available
                sh 'docker-compose --version' // Verify Docker Compose is available
                sh 'docker-compose build'
            }
        }
    }
}
