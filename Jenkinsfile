pipeline {
    agent {label 'master' }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning..'
                checkout scm
            }
        }
        stage('Validate') {
            steps {
                echo 'Validating..'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'

                bat 'node -v'
                bat 'npm prune'
                bat 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
          bat 'This will always run'
        }
        success {
          bat 'This will run only if successful'
        }
        failure {
          bat 'This will run only if failed'
        }
        unstable {
          bat 'This will run only if the run was marked as unstable'
        }
        changed {
          bat 'This will run only if the state of the Pipeline has changed'
          bat 'For example, the Pipeline was previously failing but is now successful'
        }
    }
}

