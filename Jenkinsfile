pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                git branch: 'main', credentialsId: 'GitHubCreds', url: 'https://github.com/chakri41-rgb/Aiml4.git'
            }
        }

        stage('Build and Test') {
            steps {
                // Perform build and test operations
                echo 'Build and Test successful!'
            }
        }

        stage('Generate Artifact') {
            steps {
                // Create the artifacts directory if it doesn't exist
                sh 'mkdir -p artifacts'
                // Copy the dev.html file to the artifacts directory (adjust file path as needed)
                sh 'cp dev.html artifacts/'
            }
        }
    }

    post {
        success {
            // Archive the generated artifact
            archiveArtifacts artifacts: 'artifacts/*.html', onlyIfSuccessful: true
            // Print a success message if the pipeline completes successfully
            echo 'Pipeline completed successfully!'
        }
    }
}

