pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Anzal246/DA.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('welcome-react') {
                    sh 'node -v'
                    sh 'npm -v'
                    sh 'npm install'
                }
            }
        }

        stage('Build React App') {
            steps {
                dir('welcome-react') {
                    sh 'npm run build'
                }
            }
        }
    }

    post {
        failure {
            echo "Build failed ❌"
        }
        success {
            echo "Build successful ✅"
        }
    }
}
