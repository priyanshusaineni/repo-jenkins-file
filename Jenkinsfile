pipeline {
    agent any

    parameters {
        string(name: 'TRIGGERED_REPO', defaultValue: '', description: 'Repo that triggered the build')
    }

    environment {
        FRONTEND_REPO = "https://github.com/priyanshusaineni/repo-1.git"
        BACKEND_REPO = "https://github.com/priyanshusaineni/repo-2.git"
    }

    stages {
        stage('Detect Triggered Repository') {
            steps {
                script {
                    if (params.TRIGGERED_REPO == 'repo-1') {
                        echo " Change detected in FRONTEND repository: ${FRONTEND_REPO}"
                    } else if (params.TRIGGERED_REPO == 'repo-2') {
                        echo " Change detected in BACKEND repository: ${BACKEND_REPO}"
                    } else {
                        echo " Unknown repository: '${params.TRIGGERED_REPO}'"
                        error(" No valid repository was specified in the TRIGGERED_REPO parameter.")
                    }
                }
            }
        }
    }
}
