pipeline {
    agent any
    
    environment {
        // Define environment variables here
        VARIABLE_1 = ''
    }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        
        stage('Load Variables') {
            steps {
                script {
                    // Assign a value to variable1
                    def variable1 = "This is the value of variable1"

                    // Debug print
                    echo "Variable 1: ${variable1}"

                    // Set variable1 as an environment variable
                    env.VARIABLE_1 = variable1

                    // Return variable1 for use in the next stage
                    return variable1
                }
            }
        }

        stage('Next Stage') {
            steps {
                script {
                    // Access the environment variable
                    def valueOfVariable1 = env.VARIABLE_1
                    echo "Value of Variable 1 in the next stage: ${valueOfVariable1}"
                }
            }
        }

        // Add more stages as needed...

    }
    
    post {
        failure {
            echo "Pipeline failed! Do something here..."
        }
    }
}
