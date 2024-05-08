pipeline {
    agent any // Specifies that the pipeline can run on any available agent/node
    
    // Triggers the pipeline to run periodically using the SCM polling strategy
    triggers {
        pollSCM('* * * * *') // Poll SCM every minute
    }
    
    stages {
        stage('Build') { // Defines the "Build" stage
            steps {
                echo '''
                Stage 1: Build
                Task: Build the code using a build automation tool to compile and package your code.
                Tool: vS
                '''
            }
        }
        stage('Unit and Integration Tests') { // Defines the "Unit and Integration Tests" stage
            steps {
                echo '''
                Stage 2: Unit and Integration Tests
                Task: Run unit tests to ensure the code functions as expected .
                Tools: trello , 
                '''
            }
        }
        stage('Code Analysis') { // Defines the "Code Analysis" stage
            steps {
                echo '''
                Stage 3: Code Analysis
                Task: Integrate a code analysis tool to analyze the code.
                Tool: sonar
                '''
            }
        }
        stage('Security Scan') { // Defines the "Security Scan" stage
            steps {
                echo '''
                Stage 4: Security Scan
                Task: Perform a security scan.
                Tool: OWASP.
                '''
            }
        }
        stage('Deploy to Staging') { // Defines the "Deploy to Staging" stage
            steps {
                echo '''
                Stage 5: Deploy to Staging
                Task: Deploy the application to a staging server.
                Tool: AWS.
                '''
            }
        }
        stage('Integration Tests on Staging') { // Defines the "Integration Tests on Staging" stage
            steps {
                echo '''
                Stage 6: Integration Tests on Staging
                Task: Run integration tests on the staging environment.
                Tool: trello
                '''
            }
        }
        stage('Deploy to Production') { // Defines the "Deploy to Production" stage
            steps {
                echo '''
                Stage 7: Deploy to Production
                Task: Deploy the application to a production server.
                Tool: AWS.
                '''
            }
        }
    }
    
    post {
        always {
            // Send email notification with pipeline status
            // emailext attachLog: true, // Attach the build log (Note: this line is commented out as the emailext plugin is not working)
            mail to: 'qasimziak33@gmail.com', // Recipient email address
                 subject: 'Pipeline Status', // Email subject
                 body: "The pipeline has completed. Status: ${currentBuild.currentResult}", // Email body
                 from: 'qasimziak85@gmail.com' // Sender email address
        }
    }
}
