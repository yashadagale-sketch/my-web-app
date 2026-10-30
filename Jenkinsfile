pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'test -f index.html'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the application...'
                sh 'grep -q "Hello Professor!" index.html'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'mkdir -p deployment'
                sh 'cp index.html deployment/'
                archiveArtifacts artifacts: 'deployment/index.html'
            }
        }
    }
}
