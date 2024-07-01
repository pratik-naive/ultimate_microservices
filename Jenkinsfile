pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {
                        withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                            sh "docker build -t vikashashoke/cartservice:latest ."
                        }
                    }
                }
            }
        }
