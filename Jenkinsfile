pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }
    stages{
        stage('Build'){
            steps{
                echo "Testing"
            }
        }
        stage('Test'){
            steps{
                echo "Testing"
            }
        }
        stage(Deploy){
            steps{
                echo "Deploying"
            }
        }
    }
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
    }
}