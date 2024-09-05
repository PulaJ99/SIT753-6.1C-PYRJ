pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'back_end/code_base'
        TESTING_ENVIRONMENT = 'TEST SETUP'
        PRODUCTION_ENVIRONMENT = 'PULUNUWAN YASISURU RUBASIN JAYASEKERA'
    
    }

    stages{
        stage('Build'){
            steps {
                echo " Stage: Build"
                echo "Build the code using a build automation tool to compile and package your code"
                echo "Tools: Maven, NPM"
            }
        }
        stage('Unit and Integration Tests'){
            steps {
                echo " Stage: Unit and Integration Tests"
                echo "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected."
                echo "Tools: JUnit, Selenium "
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Unit and and Integration Testing ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Unit and Integration testing status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Unit and and Integration Testing ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Unit and Integration testing status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
            }
        }
        stage('Code Analysis'){
            steps {
                echo " Stage: Code Analysis"
                echo "Integrate a code analysis tool to analyse the code and ensure it meets industry standards."
                echo "Tools: SonarQube, PMD"
            }
        }
        stage ('Security Scan'){
            steps {
                echo " Stage: Security Scan"
                echo "Perform a security scan on the code using a tool to identify any vulnerabilities."
                echo "Tools: Orca, Snyk"
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scanning ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Security scanning status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scanning ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Security scanning status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
            }
        }
        stage ('Deploy to staging'){
            steps {
                echo " Stage: Deploy to Staging"
                echo "Deploy the application to a staging server (e.g., AWS EC2 instance"
                echo "Tools: Ansible, Puppet"
            }
        }
        stage ('Integration Tests on Staging'){
            steps {
                echo "Integration Tests on Staging"
                echo "Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment"
                echo "Tools: Selenium, Jmeter, Postman"
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Integration Testing on Staging ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Integration Testing on Staging status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Integration Testing on Staging ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The Integration Testing on Staging status: ${currentBuild.result}.\n" +
                                   "Check the attached logs for more details.",
                             attachLog: true
                }
            }
        }
        stage ('Deploy to Production'){
            steps {
                echo "Deploy to Production"
                echo "Deploy the application to a production server"
                echo "Tools: Ansible, Puppet"
            }
        }
    }
}