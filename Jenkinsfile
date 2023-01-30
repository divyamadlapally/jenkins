pipeline {
    agent {
        label 'ANSIBLE'
    }

    environment {
        ENV_URL = "pipeline.global.com"        // Declaring at pipeline will allow all the stages to allow this variable
        SSH_CRED = credentials ('SSH_CRED')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3')) 
        disableConcurrentBuilds()
        disableResume()
        timeout(time: 3, unit: 'MINUTES')
        }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    tools {
        maven 'mvn 387' 
    }
     
        stages{
            stage('parallel-stage') {
                parallel {
                    stage('One') {
                        when { 
                            environment name: 'CHOICE', value: 'one' 
                        }
    
                        steps {
                            echo "I am Stage One Step"
                            echo "ENV_URL is ${ENV_URL}"   // Declaring at stage will allow only that stage to access the variable
                            sh "mvn --version"
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
                             echo I am using pipeline syntax generator
                            env
                            '''
                
                            }
                     }
                 }
            } 
        }
    }      