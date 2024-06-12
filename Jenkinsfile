pipeline { // Define the pipeline

  agent any // Run on any available Jenkins agent

  triggers {
    githubBranches( // Trigger on pushes to specific branches
        branches: 'master' // Replace 'master' with your branch names (comma-separated)
    )
}

  stages { // Define pipeline stages
    stage('Checkout') { // Stage for checking out code from GitHub
      steps {
        script {
          if (params.CREDENTIALS_ID) {
            // Use Jenkins credentials if defined (recommended)
            withCredentials([usernamePassword(credentialsId: params.CREDENTIALS_ID, passwordVariable: 'GIT_PASSWORD')]) {
              git branch: 'master', // Specify branch to checkout
                url: 'https://github.com/<username>/<repository>.git' // Replace with your repository URL
            }
          } else {
            // Use PAT directly (not recommended for security)
            // Make sure the PAT value is enclosed in single quotes and matches your actual PAT
            git branch: 'master',
              url: 'https://github.com/<username>/<repository>.git',
              credentialsId: 'your_github_pat' // Replace with your PAT
          }
        }
      }
    }

    stage('Build') { // Stage for building your project
      steps {
        script {
          // Replace with your project's build command (e.g., Maven, Gradle)
          sh 'mvn clean install' // Example for Maven
        }
      }
    }

    stage('Test') { // Stage for running unit tests
      steps {
        script {
          // Replace with your project's test command
          sh 'mvn test' // Example for Maven
        }
      }
    }
  }
}
