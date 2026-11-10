// this are pre-build section
pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }

    environment{
        COURSE = "Jenkins"
    }

    options {
        // timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // this is build section
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                         echo "Building"
                         echo $COURSE
                         #env
                         #sleep 10

                         echo "Hello ${params.PERSON}"
                         echo "Biography: ${params.BIOGRAPHY}"
                         echo "Toggle: ${params.TOGGLE}"
                         echo "Choice: ${params.CHOICE}"
                         echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('Test'){
            steps{
                script{
                    sh """
                         echo "Testing"
                    """
                }
            }
        }
        stage('Deploy'){

            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "Kiran"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }

            steps{
                script{
                    sh """
                         echo "Deploying"
                    """
                }
            }
        }
    }

    post{
        always{
            echo 'I will always say Hello again!'
            cleanWs()
        }

        success{
            echo "I will run if SUCCESS"
        }

        failure{
            echo "I will run if FAILURE"
        }

        // aborted{
        //     echo "Pipeline is Aborrted please Check"
        // }
    }
}