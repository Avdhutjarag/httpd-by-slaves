pipeline {
    agent any
    stages {
        stage('Load Variables') {
            steps {
                script {
                    // Use 'node' to provide the necessary context
                    node {
                        // Checkout the Git repository to get the Jenkinsfile
                        checkout scm

                        // Read the variables from the external file using readFile
                        def variablesContent = readFile('variables.groovy')
                        def variables = evaluate(variablesContent)

                        // Now you can use the variables in subsequent steps
                        echo "Variable 1: ${variables?.variable1}"
                        echo "Variable 2: ${variables?.variable2}"
                        echo "Variable 3: ${variables?.variable3}"
                        echo "Variable 4: ${variables?.variable4?.join(', ')}"

                        // You can use the variables in shell commands or other steps
                        sh "echo ${variables?.variable1}"

                        // Or in other Groovy code
                        def length = variables?.variable2?.length()
                        echo "Length of Variable 2: ${length}"
                    }
                }
            }
        }
        // Add other stages as needed
    }
}
