pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'devops_zal'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/movix01/DevOps_zal.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("${env.DOCKER_IMAGE}:latest").run("-p 5000:5000")
                }
            }
        }
    }
}
