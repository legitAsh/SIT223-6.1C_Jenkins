pipeline {
    agent any
    tools{
        maven 'Default' 
    }    
    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                /*script{
                    def mvnHome = tool name: 'Default', type: 'maven'
                }*/
                echo 'Building the project...'
                //sh 'mvn clean package' // Assuming Maven is used for build automation
            }
        }

        // Stage 2: Unit and Integration Tests
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
               // sh 'mvn test' // Assuming JUnit or TestNG is used for tests
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...'
                //sh 'mvn sonar:sonar' // Assuming SonarQube for code analysis
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
              //  sh 'dependency-check.sh --project example' // OWASP Dependency-Check tool
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
             //   sh 'aws ec2 deploy my-app' // Assuming deployment to AWS EC2
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
             //   sh 'postman run tests' // Postman for API tests on staging
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
           //     sh 'kubectl apply -f my-app.yaml' // Deploying with Kubernetes
            }
        }
    }

    post {
        success{
            emailext(
                to: 'briantest610@gmail.com',
                subject: "SUCCESS: Pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Pipeline completed. Please check the logs for details at: ${env.BUILD_URL}.",
                attachmentsPattern: '**/Attachment.txt'
            )
        }
         
        failure{
            emailext(
                to: 'briantest610@gmail.com',
                subject: "FAILURE: Pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The pipeline has failed. Check the build log at: ${env.BUILD_URL}",
                attachmentsPattern: '**/Attachment.txt'
               )
        }   
        always {
            emailext (
                to: 'briantest610@gmail.com',
                subject: "Jenkins: Pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Pipeline execution details are attached.",
                attachmentsPattern: '**/Attachment.txt'
               )
            }        
         }
   }
