pipeline {

    agent any

    stages {
        stage('Building/Deploying') {
            steps {
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker compose up -d --build'
                    sh 'docker compose push'
                }
            }
        }
        stage('Removing all') {
            
            steps {
                sh 'docker compose down -v '
            }
        }
    }
    post {
        // Clean after build
        always {
            cleanWs()
        }
    }
}