pipeline {
    agent any  // Use any available agent

    tools {
        gradle 'Gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK'        // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                // *** IMPORTANT: CHANGE THIS URL TO YOUR REPO URL ***
                git branch: 'master', url: 'https://github.com/ankithaPrabhakar/GradleJenkinsPipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Run Gradle build
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                sh 'gradle run' // Run the main application
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
