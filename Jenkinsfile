pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {
                        withDockerRegistry([credentialsId: 'docker-cred', url: 'https://hub.docker.com/']) {
                            sh "docker build -t vikashashoke/cartservice:latest ."
                        }
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry([credentialsId: 'docker-cred', url: 'https://hub.docker.com/']) {
                        sh "docker push vikashashoke/cartservice:latest"
                    }
                }
            }
        }
    }
}
