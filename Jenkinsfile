pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-id', toolName: 'docker') {
                        sh "docker build -t mdsurem/emailservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-id', toolName: 'docker') {
                        sh "docker push mdsurem/emailservice:latest "
                    }
                }
            }
        }
    }
}
