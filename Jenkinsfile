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
        timeout(time: 10, unit: 'SECONDS') 
    }
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Building"
                        echo $COURSE
                        // env
                        sleep 10

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