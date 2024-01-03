// Jenkinsfile

def myStringVariable = load 'variables.groovy'

pipeline {
    agent any 
    stages {
        stage('Example') {
            steps {
                script {
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
}
