pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials ('vercel_token')
    }

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
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
        stage('Build') {
            steps {
                echo 'Building...'
                // Add your deployment commands here
                bat 'npm run build'
            }
            
        stage('Deploy') {
            steps {
                echo 'deploying...'
                // Add your deployment commands here
                bat 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Add cleanup commands here
        }
    }
}
}
