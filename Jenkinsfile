pipeline {
    agent any
    tools {
        nodejs 'NodeJS'
    }
    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "No tests yet — skipping"'
            }
        }
        stage('Done') {
            steps {
                sh 'echo "Pipeline completed successfully!"'
            }
        }
    }
}