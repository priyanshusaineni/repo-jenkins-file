pipeline {
    agent any

    environment {
        FRONTEND_REPO = "https://github.com/priyanshusaineni/repo-1.git"
        BACKEND_REPO  = "https://github.com/priyanshusaineni/repo-2.git"
        WORKDIR = "multi-repo-project"
    }

    stages {
        stage('Prepare') {
            steps {
                deleteDir()
                sh "mkdir -p ${WORKDIR}"
            }
        }

        stage('Clone Changed Repo') {
            steps {
                script {
                    def repoUrl = sh(script: 'git config --get remote.origin.url', returnStdout: true).trim()
                    echo "Triggered by repo: ${repoUrl}"
                }
            }
        }
    }
}