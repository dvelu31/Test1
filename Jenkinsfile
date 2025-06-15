pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token',
                    url: 'https://github.com/your-username/your-simple-app-repo.git',
                    branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo "Building the application..."
                // Example: run a build command (e.g., for a Node.js app)
                // sh 'npm install'
                // sh 'npm build'
                sh 'echo \"Build complete!\"'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                // Example: run tests
                // sh 'npm test'
                sh 'echo \"Tests passed successfully!\"'
                // sh 'exit 1'  // Uncomment to simulate a failure
            }
        }
        stage('Archive Artifacts') {
            steps {
                echo "Archiving artifacts..."
                archiveArtifacts artifacts: 'target/*.jar, build/*.zip', fingerprint: true, allowEmptyArchive: true
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished. Check build status.'
        }
        success {
            echo 'Build was successful! 🎉'
        }
        failure {
            echo 'Build failed! ❌'
        }
    }
}
