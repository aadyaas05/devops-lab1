pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'docker build -t devops-lab-app .'
            }
        }

        stage('Test') {
            steps {
                sh 'docker run --rm devops-lab-app'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d --name devops-lab-container devops-lab-app'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
