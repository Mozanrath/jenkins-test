pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checkout handled by Jenkins SCM configuration.'
                script {
                    echo 'Current branch: ${env.BRANCH_NAME}' // Example of using SCM variable
                    echo 'Current commit: ${env.GIT_COMMIT}'  // Example of using SCM variable
                }
            }
        }
        stage('Verify File Exists') { 
            steps {
                echo 'Verifying file presence...'
                sh 'ls -la' // List files in the workspace
                sh 'cat index.html' // Print the content of index.html
                echo 'Initial verification complete.'
            }
        }
        stage('Validate HTML Content') { 
            steps {
                echo 'Validating specific content in index.html...'
                // This command will succeed (exit code 0) if the string is found.
                // If the string is NOT found, grep -q will exit with 1,
                // causing the 'sh' step and thus the stage to fail.
                sh 'grep -q "Hello, World!" index.html'
                echo 'Required content found in index.html.'
            }
        }
        stage('Simple Echo') {
            steps {
                echo 'Jenkins job with Jenkinsfile ran successfully!' // This stage won't run if the previous one fails
            }
        }
    }
}
