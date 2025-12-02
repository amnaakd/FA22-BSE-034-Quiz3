pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java HelloWorld'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'HelloWorld.class', fingerprint: true
            }
        }
    }
    post { always { junit allowEmptyResults: true, testResults: '' } }
}
