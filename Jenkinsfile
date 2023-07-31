pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                script {
                    checkout scm
                }
            }
        }

        stage('Build') {
            when {
                // Run this stage only if the branch is 'master' or 'development'
                anyOf {
                    branch 'master'
                    branch 'development'
                }
            }
            steps {
                // Add build steps for your application here
                echo 'Building the application...'
            }
        }

        stage('Test') {
            when {
                // Run this stage for all branches
                expression {
                    return true
                }
            }
            steps {
                // Add test steps for your application here
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            when {
                // Run this stage only if the branch is 'master'
                branch 'master'
            }
            steps {
                // Add deployment steps for your application here
                echo 'Deploying the application...'
            }
        }
    }

    post {
        // Define post-build actions, if required
        always {
            echo 'Pipeline completed!'
        }
    }
}
