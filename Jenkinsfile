// Testing comments
pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'back_end/code_base'
        TESTING_ENVIRONMENT = 'TEST SETUP'
        PRODUCTION_ENVIRONMENT = 'PULUNUWAN YASISURU RUBASIN JAYASEKERA'
    
    }
    // comment added
    stages{
        stage('Build'){
            steps {
                echo "fetch the source code from ${env.DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scan ${currentBuild.result}: ${currentBuild.fullDisplayName}",
                             body: "The security scan completed successfully.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scan FAILED: ${currentBuild.fullDisplayName}",
                             body: "The security scan failed. Check the attached logs.",
                             attachLog: true
                }
            }
        }
        stage('Test'){
            steps {
                echo "unit tests"
                echo "integration tests"
            }
        }
        stage('Code Quality Check'){
            steps {
                echo "check the quality of the code"
            }
        }
        stage ('Deploy'){
            steps {
                echo "deploy the application to a testing environment : ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage ('Approval'){
            steps {
                echo "Approval required"
                sleep(10)
            }
        }
        stage ('Deploy to Production'){
            steps {
                echo "Deploy the code to production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
