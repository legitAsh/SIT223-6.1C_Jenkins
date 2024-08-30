pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis with Checkstyle...'
                sh 'mvn checkstyle:checkstyle'
                // Archive Checkstyle results
                archiveArtifacts artifacts: 'target/checkstyle-result.xml', allowEmptyArchive: true
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Update this path to the actual location of your security scan script
                sh '/path/to/dependency-check.sh --project example'
            }
        }
        stage('Deploy to Staging') {
            when {
                expression { currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying to Staging...'
                // Deployment steps
            }
        }
        stage('Integration Tests on Staging') {
            when {
                expression { currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Running integration tests on Staging...'
                // Integration tests steps
            }
        }
        stage('Deploy to Production') {
            when {
                expression { currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying to Production...'
                // Deployment steps
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
            emailext (
                subject: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                body: "Good news! The build ${env.JOB_NAME} ${env.BUILD_NUMBER} has succeeded.",
                to: 'briantest610@gmail.com'
            )
        }
        failure {
            echo 'Pipeline failed!'
            emailext (
                subject: "Build Failure: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                body: "Unfortunately, the build ${env.JOB_NAME} ${env.BUILD_NUMBER} has failed.",
                to: 'briantest610@gmail.com'
            )
        }
    }
}
