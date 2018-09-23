pipeline {
    agent any
    stages {
        stage('Build') {
            agent none
            steps {
                step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
            }
        }
        stage('Test') {
            agent {
                docker { image 'node:7-alpine' } 
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
