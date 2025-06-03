pipeline {
    agent any // This means Jenkins can use any available agent/executor

    stages {
        stage('Checkout') {
            steps {
                // Jenkins automatically checks out the code from the SCM configured
                // in the job when using "Pipeline script from SCM"
                echo 'Code checkout handled by Jenkins SCM configuration.'
                script {
                    // If you need to access SCM variables like GIT_BRANCH, GIT_COMMIT
                    // they are available. For example:
                    // echo "Building branch: ${env.GIT_BRANCH}"
                    echo 'Script block placeholder'
                }
            }
        }
        stage('Verify Content') {
            steps {
                echo 'Verifying content...'
                sh 'ls -la' // List files in the workspace
                sh 'cat index.html' // Print the content of index.html
                echo 'Verification complete.'
            }
        }
        stage('Simple Echo') {
            steps {
                echo 'Jenkins job with Jenkinsfile ran successfully!'
            }
        }
    }
}
