pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application using Maven...'
                // Maven is a build automation tool used primarily for Java projects.
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using JUnit and integration tests using Mockito...'
                // JUnit is used for unit testing in Java, and Mockito is used for mocking in integration tests.
            }
            post {
                success {
                    emailext subject: "Jenkins Build Successful: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                             body: "Good news! The build ${env.BUILD_NUMBER} of job ${env.JOB_NAME} passed the Unit and Integration Tests stage.",
                             to: "s222166472@deakin.edu.au",
                             attachLog: true
                }
                failure {
                    emailext subject: "Jenkins Build Failed: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                             body: "Oops! The build ${env.BUILD_NUMBER} of job ${env.JOB_NAME} failed at the Unit and Integration Tests stage. Check the logs for details.",
                             to: "s222166472@deakin.edu.au",
                             attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code using SonarQube...'
                // SonarQube is a popular code quality and security analysis tool.
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check...'
                // OWASP Dependency-Check is a tool that identifies project dependencies and checks if there are any known, publicly disclosed vulnerabilities.
            }
            post {
                success {
                    emailext subject: "Jenkins Build Successful: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                             body: "Good news! The build ${env.BUILD_NUMBER} of job ${env.JOB_NAME} passed the Security Scan stage.",
                             to: "s222166472@deakin.edu.au",
                             attachLog: true
                }
                failure {
                    emailext subject: "Jenkins Build Failed: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                             body: "Oops! The build ${env.BUILD_NUMBER} of job ${env.JOB_NAME} failed at the Security Scan stage. Check the logs for details.",
                             to: "s222166472@deakin.edu.au",
                             attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging environment using AWS CLI...'
                // AWS CLI (Command Line Interface) can be used to deploy applications to AWS services such as EC2 instances.
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment using Selenium...'
                // Selenium is a tool for automating web browsers, often used for testing web applications.
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to the production environment using Ansible...'
                // Ansible is an automation tool for configuration management, application deployment, and task automation.
            }
        }
    }
}
