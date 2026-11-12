// pre-build stage
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
        timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

// build stage
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Building"
                        echo "$COURSE"
                        #sleep 10
                        env

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
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Kiran', description: 'Who should I say hello to?')
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

// post build stage
    post{
        always{
            echo "I will always say Hello again!"
            cleanWs()
        }
        success{
            echo "I will run if success"
        }
        failure{
            echo "I will run if failure"
        }
        // aborted{
        //     echo "Pipeline is Aborted please Check It"
        // }
    }
}