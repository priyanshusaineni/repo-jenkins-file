pipeline {
    agent any
    parameters {
        string(name: 'REPO_NAME', defaultValue: '', description: 'Triggered repository name')
    }
    stages {
        stage('Display Trigger Source') {
            steps {
                echo "Triggered by repository: ${params.REPO_NAME}"
            }
        }
    }
}
