pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm [cite: 33]
            }
        }
        stage('Build & Test') {
            steps {
                echo 'Running Python Application...'
                sh 'python3 main.py' [cite: 33]
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'main.py', fingerprint: true [cite: 35]
            }
        }
    }
    post {
        always {
            echo 'Build finished. Sending notification...'
        }
    }
}
