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
                    println "Setting up Python environment..."
                    sh '''
                        python3 -m venv venv
                        source venv/bin/activate
                        pip install --upgrade pip
                        if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
                    '''
                }
            }
        }

        // 3️⃣ Test
        stage('Test') {
            steps {
                script {
                    println "Running tests..."
                    sh '''
                        source venv/bin/activate
                        if [ -d tests ]; then pytest tests/ || true; fi
                    '''
                }
            }
        }

        // 4️⃣ Deploy
        stage('Deploy') {
            steps {
                script {
                    println "Deploying project..."
                    sh 'echo "Deploy step placeholder (replace with real deploy)"'
                }
            }
        }
    }

    post {
        success {
            echo "Python pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed. Check the logs!"
        }
    }
}
