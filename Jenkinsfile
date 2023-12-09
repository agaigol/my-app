pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Dockerize') {
            steps {
                script {
                    sh 'docker build -t my-java-app:latest .'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -p 8080:8080 my-java-app:latest'
                }
            }
        }
    }
}
