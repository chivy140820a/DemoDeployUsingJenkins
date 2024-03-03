pipeline {
    agent any
    stages {
        stage('Building/Deploying') {
            steps {
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker ps'
                }
            }
        }
    }
}