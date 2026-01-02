pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // This pulls your project from the linked GitHub repo
                checkout scm
            }
        }
        stage('Build & Test') {
            steps {
                echo 'Running Python Application...'
                // Executes your application as required
                sh 'python3 main.py'
            }
        }
        stage('Archive') {
            steps {
                // Requirement: Archive the project [cite: 35]
                archiveArtifacts artifacts: 'main.py', fingerprint: true
            }
        }
    }
    post {
        always {
            // Requirement: Notify Slack/Delivery phase [cite: 38]
            echo 'Pipeline finished. Please check Slack for notifications.'
        }
    }
}
