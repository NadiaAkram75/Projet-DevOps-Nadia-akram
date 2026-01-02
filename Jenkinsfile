pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build & Test') {
            steps {
                echo 'Running Python Application...'
                sh 'python3 main.py'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'main.py', fingerprint: true
            }
        }
    }
}
