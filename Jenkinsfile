pipeline {
    agent any

    triggers {
        cron('*/1 * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                // Add your code checkout steps here, e.g.,
                // git url: 'https://github.com/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build steps here, e.g.,
                // sh 'make build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test steps here, e.g.,
                // sh 'make test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deploy steps here, e.g.,
                // sh 'make deploy'
            }
        }

        stage('Hello') {
            steps {
                echo 'Hello World'
                echo 'Hello World 2'
                echo 'Hello World changed'
            }
        }
    }
}
