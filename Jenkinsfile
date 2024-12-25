pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Execute Batch Script') {
            steps {
                script {
                    // Ensure the script is executable (in case it's not already)
                    echo "Making batch script executable..."
                    bat 'chmod +x list_files.sh' // Optional, for compatibility

                    // Print current directory to confirm workspace
                    echo "Current directory is: "
                    bat 'echo %cd%'

                    // List files in the current directory (Windows command)
                    echo "Listing files in the current directory:"
                    bat 'dir'

                    // Try executing the bash script with bash if available
                    echo "Executing list_files.sh script:"
                    def result = ''
                    if (isUnix()) {
                        result = sh(script: 'bash list_files.sh', returnStdout: true).trim()
                    } else {
                        result = bat(script: 'list_files.sh', returnStdout: true).trim()
                    }

                    // Print the output to the Jenkins console
                    echo "The result of the script is: \n${result}"
                }
            }
        }
    }
}
