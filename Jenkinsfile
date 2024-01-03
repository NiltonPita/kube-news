pipeline {
    agent any

    stages {
        stage("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("fabricioveronez/live-kube-news:v1", '-f ./src/Dockerfile ./src')
                }
            }
        }

        stage("Push Docker Image") {
            steps {
                script {
                    docker.wothRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push('latest')
                        dockerapp.push('v1')
                    }
                }
            }
        }

        stage("Deploy no Kubernetes") {
            steps {
                sh "echo 'Deploy no Kubernetes'"
            }
        }
    }
}