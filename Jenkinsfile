// pre-build
pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }
// build
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "Building"
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
    }
}