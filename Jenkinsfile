# pre-build
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
    post{
        always{
            echo "I will say hello again"
        }
        success{

        }
        failure{
            
        }
    }
}