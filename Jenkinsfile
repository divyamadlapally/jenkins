pipeline {
    agent any
    stages{
        stage('One') {
            steps {
                echo "I am Stage One Step"
            }
        }
        stage('Two') {
            steps {
                echo "I am Stage Two Step"
            }
        }
        stage('Three') {
            steps {
                echo "I am Stage Three Step"
                sh '''Hai world
                      Hello world
                      I am using pipeline syntax generator'''
            }
        }
    }
} 