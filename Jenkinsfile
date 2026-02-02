pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/madagoni-bharath-kumar/calculator-app.git'
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build and tests successful'
            archiveArtifacts artifacts: 'target/*.jar'
        }
        failure {
            echo 'Build failed'
        }
    }
}
