// pre build 
pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }

// build
    environment{
        COURSE = "Jenkins-CICD"
    }
    options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Building"
                        echo $COURSE
                        env
                        sleep 10

                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
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
        stage(Deploy){
            // input {
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "Kiran"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //     }
            // }
            when{
                expression { "$params.DEPLOY"}
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
// post build
    post{
        always{
            echo 'I will always say Hello again!'
            cleanWs()
        }
        success{
            echo "I WILL RUN IF SUCCESS"
        }
        failure{
            echo "I WILL RUN IF FAILURE"
        }
        aborted{
            echo "Pipeline is Aborted please Check"
        }
    }
}