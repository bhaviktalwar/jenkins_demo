pipeline {
    agent any

    environment {
        STAGING_ENV = "Staging-Server"
        PRODUCTION_ENV = "Bhavik_Talwar_Production"
        NOTIFY_EMAIL = "your-email@gmail.com"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building the application using a build automation tool like Maven"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests using JUnit"
                echo "Running integration tests to validate component interaction"
            }
            post {
                always {
                    echo "Sending email notification for Test stage"
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Performing static code analysis using SonarQube"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Scanning application for vulnerabilities using OWASP Dependency-Check"
            }
            post {
                always {
                    echo "Sending email notification for Security Scan stage"
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying application to staging environment (e.g., AWS EC2)"
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging environment"
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying application to production environment: ${PRODUCTION_ENV}"
            }
        }
    }
}

