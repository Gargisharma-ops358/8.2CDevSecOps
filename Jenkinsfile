pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Gargisharma-ops358/8.2CDevSecOps.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                sh 'npm run coverage || true'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                sh 'npm audit || true'
            }
        }

        stage('SonarCloud Analysis') {
            steps {
                withCredentials([
                    string(credentialsId: 'SONAR_TOKEN', variable: 'SONAR_TOKEN')
                ]) {
                    sh '''
                        npm install -g sonarqube-scanner

                        sonar-scanner \
                          -Dsonar.projectKey=8.2CDevSecOps \
                          -Dsonar.organization=gargisharma-ops358 \
                          -Dsonar.host.url=https://sonarcloud.io \
                          -Dsonar.token=$SONAR_TOKEN
                    '''
                }
            }
        }
    }
}
