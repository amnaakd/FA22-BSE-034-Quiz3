pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Run Python') {
            steps {
                sh 'python3 hello.py'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'hello.py', fingerprint: true
            }
        }
    }
}
