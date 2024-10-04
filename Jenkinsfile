pipeline {
    agent {
        label 'AGENT-1'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo this is buld'
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy'
            }
        }
    }
}