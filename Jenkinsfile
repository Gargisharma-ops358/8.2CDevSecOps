pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build: Compile and package code using Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Testing: Run unit and integration tests using JUnit'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Code Analysis: Analyse code using SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Security Scan: Scan for vulnerabilities using Snyk'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging: Deploy application to AWS EC2 staging server'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Staging Tests: Run integration tests using Selenium'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production: Deploy application to AWS EC2 production server'
            }
        }
    }
}
