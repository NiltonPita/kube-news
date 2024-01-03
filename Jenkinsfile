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
                sh "echo 'Envio da Imagem'"
            }
        }

        stage("Deploy no Kubernetes") {
            steps {
                sh "echo 'Deploy no Kubernetes'"
            }
        }
    }
}