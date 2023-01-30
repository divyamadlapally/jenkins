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
                sh '''
                echo Hai world
                echo Hello world
                echo I am using pipeline syntax generator'''
            }
        }
    }
} 