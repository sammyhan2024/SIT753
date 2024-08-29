pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example: sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example: sh 'mvn test'
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
                echo 'Analyzing the code...'
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example: sh 'dependency-check.sh'
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
                echo 'Deploying to staging environment...'
                // Example: sh 'ansible-playbook deploy.yml -i staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example: sh 'mvn verify -Pstaging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Example: sh 'ansible-playbook deploy.yml -i production'
            }
        }
    }
}
