/*pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Add your build steps here
                // e.g., sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Add your test steps here
                // e.g., sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Add your code analysis steps here
                // e.g., sh 'mvn checkstyle:checkstyle'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Add your security scan steps here
                // e.g., sh '/path/to/dependency-check.sh --project example'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Add your deployment steps here
                // e.g., sh 'deploy-to-staging.sh'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Add your integration tests steps here
                // e.g., sh 'run-integration-tests.sh'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Add your production deployment steps here
                // e.g., sh 'deploy-to-production.sh'
            }
        }
    }

    post {
        always {
            emailext(
                to: 'briantest610@gmail.com',
                subject: "Build ${currentBuild.fullDisplayName}",
                body: """\
    Build ${currentBuild.fullDisplayName} (${currentBuild.currentResult})

    Check the Jenkins console output for more details:
    ${env.BUILD_URL}""",
            attachmentsPattern: 'Attachment.txt', // Adjust this if necessary
            attachLog: true
           )
        }
    }
}
*/

pipeline {
    agent any

    stages {
        stage('Test Email') {
            steps {
                emailext(
                    to: 'briantest610@gmail.com',
                    subject: "Test Email from Jenkins",
                    body: """\
This is a test email from Jenkins to check email configuration.
Check the Jenkins console output for more details.
""",
                    attachLog: true
                )
            }
        }
    }
}
