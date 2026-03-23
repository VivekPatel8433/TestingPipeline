pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    environment {
        NETLIFY_AUTH_TOKEN = credentials('netlify-auth-token-id')
        NETLIFY_SITE_ID = credentials('netlify-site-id')
    }

    stages {
        stage('Check Node') {
            steps {
                sh 'node -v && npm -v'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        // stage('Test') {
        //     steps {
        //         sh 'npm run test'
        //     }
        // }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy to Netlify') {
            steps {
                sh '''
                npx netlify deploy \
                  --prod \
                  --dir=build \
                  --site=$NETLIFY_SITE_ID \
                  --auth=$NETLIFY_AUTH_TOKEN
                '''
            }
        }
    }
}