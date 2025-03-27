pipeline {
    agent any

    tools {
        jdk 'JDK21'
        maven 'Maven3.9.9'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/sindhu2994/sindhudevops.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
            }
        }
    }

    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}