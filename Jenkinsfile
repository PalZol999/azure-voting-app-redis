pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Verify Environment') {
            steps {
                sh 'printenv'
                sh 'echo $PATH'
                sh 'which docker'
                sh 'docker --version'
                sh 'docker-compose --version'
            }
        }
        stage('Verify Branch') {
            steps {
                echo "${env.GIT_BRANCH}"
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker-compose build'
            }
        }
    }
}
