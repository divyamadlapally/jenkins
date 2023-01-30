pipeline {
    agent any

    environment {
        ENV_URL = "pipeline.global.com"        // Declaring at pipeline will allow all the stages to allow this variable
    }
    stages{
        stage('One') {
            steps {
                echo "I am Stage One Step"
                echo "ENV_URL is ${ENV_URL}"   // Declaring at stage will allow only that stage to access the variable
            }
        }
        stage('Two') {
             environment {
                ENV_URL = "stage2.global.com"
             }
            steps {
                echo "I am Stage Two Step"
                echo "ENV_URL is ${ENV_URL}"
            }
        }
        stage('Three') {
            steps {
                sh '''
                echo Hai world
                echo Hello world
                echo I am using pipeline syntax generator'''
            }
        }
    }
} 