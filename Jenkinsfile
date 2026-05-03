pipeline {
    agent any

    triggers {
        // Poll GitHub every 5 minutes (webhook not required)
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile and package application code.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests and integration tests for component interactions.'
                echo 'Tool: JUnit + Selenium'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Perform static code quality analysis against coding standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan source and dependencies for known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy application build to staging environment.'
                echo 'Tool: AWS CodeDeploy (to EC2)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Execute integration tests in staging environment.'
                echo 'Tool: Postman/Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy validated release from staging to production.'
                echo 'Tool: AWS CodeDeploy (to EC2)'
            }
        }
    }
}
