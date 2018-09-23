pipeline {
    agent {
        docker { image 'node:7-alpine' } 
    }
    stages {
        stage('Build') {
            agent none
            steps {
                step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
            }
        }
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
