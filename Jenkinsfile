pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = "/path/to/code"
        TESTING_ENVIRONMENT = "testing"
        PRODUCTION_ENVIRONMENT = "production"
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating any necessary artifacts"
                
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
               
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
                
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
                
            }
        }
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment using the environment variable specifying the environment name: ${env.PRODUCTION_ENVIRONMENT}"
                
            }
        }
    }

    post {
        always {
            emailext (
                subject: "Pipeline ${currentBuild.result}: ${env.JOB_NAME}",
                body: "Build Status: ${currentBuild.result}",
                to: "your_email@example.com",
                attachLog: true
            )
        }
    }

}
