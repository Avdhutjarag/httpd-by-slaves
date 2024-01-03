pipeline {
    agent any
    stages {
        stage('Load Variables') {
            steps {
                script {
                    // Use 'node' to provide the necessary context
                    node {
                        // Load the variables from the external file
                        def myStringVariable = load 'variables.groovy'

                        // Now you can use the variable in subsequent steps
                        echo "My string variable: ${myStringVariable}"

                        // You can use the variable in shell commands or other steps
                        sh "echo ${myStringVariable}"

                        // Or in other Groovy code
                        def length = myStringVariable.length()
                        echo "Length of the string: ${length}"
                    }
                }
            }
        }
        // Add other stages as needed
    }
}
