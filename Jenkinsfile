pipeline {
    agent any

    stages {
        stage('Checkout code') {
            steps {
                checkout scm 'https://github.com/DimitarRadev88/student-registry-app-configuring-jenkinsfile'
            }
        }

        stage('Install dependencies') {
            steps {
                bat 'npm install'   
            }   
        }

        stage("Start the applications") {
            steps{
                bat 'npm start'
            }
        }

        stage('Run tests') {
            steps {
                bat 'npm test'
            }    
        }

    }

    post {
        always {
            echo 'Pipeline finished.'
            cleanWs()
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        unstable {
            echo 'Pipeline was unstable (e.g., some tests failed).'
        }
    }
}