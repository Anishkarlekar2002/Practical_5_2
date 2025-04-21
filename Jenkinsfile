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
                    dir('Q3') {
                        docker.build("HelloWorld", ".")
                    }
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("HelloWorld").run()
                }
            }
        }
    }
}
