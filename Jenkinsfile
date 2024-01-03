def variables // Declare variables at the top level

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
                    try {
                        // Load variables only if not already loaded
                        if (!variables) {
                            def variablesContent = readFile('variables.groovy')
                            echo "Loaded Variables Content: ${variablesContent}"

                            variables = evaluate(variablesContent)
                            echo "Loaded Variables: ${variables}"
                        }

                        echo "Variable 1: ${variables.variable1}"
                        echo "Variable 2: ${variables.variable2}"
                        echo "Variable 3: ${variables.variable3}"
                    } catch (Exception e) {
                        echo "Error loading variables: ${e.message}"
                        currentBuild.result = 'FAILURE'
                        error "Failed to load variables"
                    }
                }
            }
        }

        stage('Use Variables in Stage 1') {
            steps {
                script {
                    echo "Using Variable 1 in Stage 1: ${variables.variable1}"
                    // Perform actions using variables in this stage
                }
            }
        }

        stage('Use Variables in Stage 2') {
            steps {
                script {
                    echo "Using Variable 2 in Stage 2: ${variables.variable2}"
                    // Perform actions using variables in this stage
                }
            }
        }

        stage('Use Variables in Stage 3') {
            steps {
                script {
                    echo "Using Variable 3 in Stage 3: ${variables.variable3}"
                    // Perform actions using variables in this stage
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
