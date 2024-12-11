pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sh '''pipeline {
    agent any

    environment {
        // Define any environment variables here
        APP_NAME = "sample-app"
        DEPLOY_ENV = "staging"
    }

    stages {
        stage(\'Checkout\') {
            steps {
                echo \'Checking out code...\'
                git url: \'https://github.com/example/sample-app.git\', branch: \'main\'
            }
        }

        stage(\'Build\') {
            steps {
                echo \'Building the application...\'
                // Example: use a build tool like Maven, Gradle, or npm
                sh \'mvn clean install\'
            }
        }

        stage(\'Test\') {
            steps {
                echo \'Running tests...\'
                // Example: run tests after the build
                sh \'mvn test\'
            }
        }

        stage(\'Deploy\') {
            steps {
                echo "Deploying the application to ${DEPLOY_ENV}..."
                // Example: deploy to a server or a cloud platform
                sh \'scp target/sample-app.jar user@server:/path/to/deploy\'
            }
        }
    }

    post {
        success {
            echo \'Pipeline completed successfully!\'
        }
        failure {
            echo \'Pipeline failed!\'
        }
    }
}
'''
        }
      }

    }
  }