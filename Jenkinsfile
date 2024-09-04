pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                // Simulating the build with Maven
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit...'
                // Simulating test run with JUnit
                echo 'Tool: JUnit'
            }
            post {
                always {
                    emailext(
                        subject: "Build #${BUILD_NUMBER} - Unit and Integration Tests Results",
                        body: "The unit and integration tests have completed. Check the console output at ${BUILD_URL}.",
                        to: 'briantest610@gmail.com',
                        attachmentsPattern: 'Attachment.txt'
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis using SonarQube...'
                // Simulating code analysis with SonarQube
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check...'
                // Simulating security scan with OWASP Dependency-Check
                echo 'Tool: OWASP Dependency-Check'
            }
            post {
                always {
                    emailext(
                        subject: "Build #${BUILD_NUMBER} - Security Scan Results",
                        body: "The security scan has completed. Check the console output at ${BUILD_URL}.",
                        to: 'briantest610@gmail.com',
                        attachmentsPattern: 'Attachment.txt'
                    )
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment using AWS EC2...'
                // Simulating deployment to staging with AWS EC2
                echo 'Tool: AWS EC2'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging using Selenium...'
                // Simulating integration tests on staging with Selenium
                echo 'Tool: Selenium'
            }
            post {
                always {
                    emailext(
                        subject: "Build #${BUILD_NUMBER} - Integration Tests on Staging Results",
                        body: "The integration tests on staging have completed. Check the console output at ${BUILD_URL}.",
                        to: 'briantest610@gmail.com',
                        attachmentsPattern: 'Attachment.txt'
                    )
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment using AWS EC2...'
                // Simulating deployment to production with AWS EC2
                echo 'Tool: AWS EC2'
            }
        }
    }
}
