pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Krutikaz/JenkinApp.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'  // Adjust build command as needed
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'  // Adjust test command as needed
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }
}