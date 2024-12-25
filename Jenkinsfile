pipeline {
    agent any
    stages {
        stage('Execute Bash Script') {
            steps {
                script {
                    // Ensure the script is executable (in case it's not)
                    sh 'chmod +x list_files.sh'
                    
                    // Execute the 'list_files.sh' script and capture its output
                    def result = sh(script: './list_files.sh', returnStdout: true).trim()
                    
                    // Print the output to the Jenkins console
                    echo "The result of the ls command is: \n${result}"
                }
            }
        }
    }
}
