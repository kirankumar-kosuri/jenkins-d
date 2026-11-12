// pre-build
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
// build
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Building"
                        echo "$COURSE"
                        #sleep 10
                        env
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
            echo "I will always say Hello again!"
            cleanWs()
        }
        success{
            echo "I will run if success"
        }
        failure{
            echo "I will run if failure"
        }
        aborted{
            echo "Pipeline is Aborted please Check It"
        }
    }
}