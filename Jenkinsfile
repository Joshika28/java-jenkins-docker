pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Joshika28/java-jenkins-docker.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t java-jenkins-docker .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker run --rm java-jenkins-docker'
            }
        }
    }
}