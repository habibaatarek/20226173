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
                    bat 'chmod +x list_files.sh' // Optional on Windows, in case it's needed for compatibility

                    // Print current directory to confirm workspace
                    echo "Current directory is: "
                    bat 'echo %cd%'

                    // List files in the current directory (Windows command)
                    echo "Listing files in the current directory:"
                    bat 'dir'

                    // Execute the batch script (if it's a bash script, use bash to execute it)
                    echo "Executing list_files.sh script:"
                    def result = bat(script: 'bash list_files.sh', returnStdout: true).trim()

                    // Print the output to the Jenkins console
                    echo "The result of the ls command is: \n${result}"
                }
            }
        }
    }
}
