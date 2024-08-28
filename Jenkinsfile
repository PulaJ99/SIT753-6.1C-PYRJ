// Testing comment
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
                echo "fetch the source code from ${env.DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
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
