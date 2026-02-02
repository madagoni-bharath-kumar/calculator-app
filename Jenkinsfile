pipeline {
    agent any

    stages {

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
