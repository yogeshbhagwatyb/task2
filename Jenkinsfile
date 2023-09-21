pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out your code from your version control system (e.g., Git).
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Use Maven to build your Java project.
                sh 'mvn clean install'
            }
        }

        // Add additional stages for testing, deploying, etc. as needed.
    }

    post {
        always {
            // Archive the build artifacts (e.g., JAR files).
            archiveArtifacts(allowEmptyArchive: true, artifacts: '**/target/*.jar')
        }
    }
}