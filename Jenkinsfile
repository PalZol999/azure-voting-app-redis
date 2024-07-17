pipeline {
    agent {
        docker {
            image 'docker:19.03.12' // Ensure this image has both Docker and Docker Compose
            args '-v /var/run/docker.sock:/var/run/docker.sock'
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
                sh 'docker-compose version' // Verify docker-compose is available
                sh 'docker-compose build'
            }
        }
    }
}
