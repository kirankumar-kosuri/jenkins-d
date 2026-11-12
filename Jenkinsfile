#pre-build
pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }
# build
    stages{
        stage('Build'){
            steps{
                echo "Building"
            }
        }
        stage('Test'){
            steps{
                echo "Testing"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying"
            }
        }
    }
#post build
    post{
        always{
            echo "I will always say Hello again!"
        }
        success{
            echo "I will run if Success"
        }
        failure{
            echo "I will run if Failure"
        }
    }
}