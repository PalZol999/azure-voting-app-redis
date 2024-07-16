pipeline {
    agent any

    stages {
        stage('Verify Environment') {
            steps {
                sh 'printenv'
                sh 'echo $PATH'
                sh 'which docker'
                sh 'docker --version'
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