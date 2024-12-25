pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the Git repository
                git branch: 'main', url: 'https://github.com/habibaatarek/Cloud'
            }
        }
        stage('Execute Bash Script') {
            steps {
                // Execute the bash script
                sh './list_files.sh'
            }
        }
    }
}
