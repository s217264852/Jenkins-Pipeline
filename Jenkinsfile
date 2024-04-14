pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using a build automation tool to compile and package your code.'
                echo 'Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests to ensure the code functions as expected and running integration tests to ensure the different components of the application work together as expected.'
                echo 'Tool: JUnit for unit tests, and JUnit or TestNG for integration tests'
            }
            post {
                success {
                    emailext(
                        to: "mcaldow98@gmail.com",
                        subject: "Unit and Integration Tests - Status Notification Email",
                        body: "Unit and Integration Tests stage was successful.",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: "mcaldow98@gmail.com",
                        subject: "Unit and Integration Tests - Status Notification Email",
                        body: "Unit and Integration Tests stage failed.",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Integrating a code analysis tool to analyse the code and ensure it meets industry standards.'
                echo 'Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing a security scan on the code using a tool to identify any vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
            post {
                success {
                    emailext(
                        to: "mcaldow98@gmail.com",
                        subject: "Security Scan - Status Notification Email",
                        body: "Security Scan stage was successful.",
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: "mcaldow98@gmail.com",
                        subject: "Security Scan - Status Notification Email",
                        body: "Security Scan stage failed.",
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to a staging server.'
                echo 'Tool: AWS EC2 for the staging server'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment to ensure the application functions as expected in a production-like environment.'
                echo 'Tool: Selenium for end-to-end tests'
            }
            post {
                success {
                    emailext(
                        to: "mcaldow98@gmail.com",
                        subject: "Integration Tests on Staging - Status Notification Email",
                        body: "Integration Tests on Staging stage was successful.",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "mcaldow98@gmail.com",
                        subject: "Integration Tests on Staging - Status Notification Email",
                        body: "Integration Tests on Staging stage failed.",
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to a production server.'
                echo 'Tool: AWS EC2 for the production server'
                echo 'This is my comment.'
            }
        }
    }
}
