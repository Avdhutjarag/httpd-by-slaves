pipeline {
    agent any
    
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        
        stage('Load Variables') {
            steps {
                script {
                    // Debug prints
                    def variablesContent = readFile('variables.groovy')
                    echo "Loaded Variables Content: ${variablesContent}"

                    def variables = evaluate(variablesContent)
                    echo "Loaded Variables: ${variables}"

                    echo "Variable 1: ${variables.variable1}"
                    echo "Variable 2: ${variables.variable2}"
                    echo "Variable 3: ${variables.variable3}"
                }
            }
        }

        // Add more stages as needed...

        stage('Your Next Stage') {
            steps {
                // Your existing or additional steps
            }
        }
    }
    
    post {
        failure {
            echo "Pipeline failed! Do something here..."
        }
    }
}
