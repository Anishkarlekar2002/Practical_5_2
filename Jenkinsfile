pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Anishkarlekar2002/Practical_5_2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("java-hello-world-app", ".")
                }
            }
        }

       stage('Run Docker Container') {
            steps {
                script {
                    def containerOutput = bat(script: 'docker run --rm java-hello-world-app', returnStdout: true).trim()
                    echo "Output from Docker container:\n${containerOutput}"
                 }
            }
        }

    }
}
