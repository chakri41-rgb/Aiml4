pipeline {
agent any
stages {
stage('Checkout') {
steps {
// Checkout the repository
git
branch:
'main',
credentialsId:
'https://github.com/chakri41-rgb/Aiml4.git'
'GitHubCreds',
url:}
}
stage('Build and Test') {
steps {
// Here you can perform any build and test operations
// For simplicity, let's just print a success message
echo 'Build and Test successful!'
}
}
stage('Generate Artifact') {
steps {
// Create the artifacts directory if it doesn't exist
sh 'mkdir -p artifacts'
// Copy the dev.html file to the artifacts directory
sh 'cp 1.html ./artifacts/'
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
