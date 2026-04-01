pipeline {
    agent any

    stages {
        // 1️⃣ Checkout
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Gopimru/Mru.git'
            }
        }

        // 2️⃣ Build
        stage('Build') {
            steps {
                script {
                    println "Building the project..."
                    sh 'echo "Simulating build step"'
                }
            }
        }

        // 3️⃣ Test
        stage('Test') {
            steps {
                script {
                    println "Running tests..."
                    sh 'echo "Simulating test step"'
                }
            }
        }

        // 4️⃣ Deploy
        stage('Deploy') {
            steps {
                script {
                    println "Deploying project..."
                    sh 'echo "Simulating deploy step"'
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed. Check logs!"
        }
    }
}
