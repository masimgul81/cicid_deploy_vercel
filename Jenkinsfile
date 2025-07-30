pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials ('vercel_token')
    }

    stages {
        stage('Install') {
            steps {
                sh 'npm install'
                // echo 'Building...'
                // Add your build commands here
            }
        }
        stage('Test') {
            steps {
                echo 'No Testing script...'
                // Add your test commands here
            }
        }

        stage('Setup') {
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'npx vercel --version'
            }
        }
        // stage('Build') {
        //     steps {
        //         sh '''
        //             export NODE_OPTIONS="--max-old-space-size=8192"
        //             npm run build --standalone
        //         '''
        //     }
        // }
        stage('Build') {
            steps {
                echo 'Building -- ho ja build0---...'
                // Add your deployment commands here
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploying...'
                // Add your deployment commands here
                sh 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    
}
}
