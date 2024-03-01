pipeline {
    agent any

    tools {
        maven 'Maven 3.5.2' // Use the Maven version named 'M3' configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm // Checks out source code from source control
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build was successful.'
        }

        failure {
            echo 'Build failed.'
        }
    }
}
