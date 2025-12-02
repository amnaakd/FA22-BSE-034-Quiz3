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
   post {
    always {
        // No JUnit reports available for this simple example.
        // If you add tests later, change the pattern to something like: junit '**/TEST-*.xml'
        echo 'Build completed.'
    }
}

