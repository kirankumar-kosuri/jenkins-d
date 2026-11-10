// pipeline {
//     agent {
//         node{
//             label "agent-1"
//         }
//     }
//     stages {
//         stage('Build') {
//             steps {
//                 echo "Building"
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo  "Testing"
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo "Deploying"
//             }
//         }
//     }
// }

pipeline{
    agent{
        node{
            label "Agent-1"
        }
    }
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
            echo 'I will always say Hello again!'
            cleanWs()
        }

        success{
            echo "I will run if SUCCESS"
        }

        failure{
            echo "I will run if FAILURE"
        }
    }
}

