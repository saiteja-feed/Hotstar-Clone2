pipeline {
    agent any

    stages {
        stage('Build and Run Docker Containers') {
            steps {
                sh 'docker compose down || true'
                sh 'docker compose build'
                sh 'docker compose up -d'
            }
        }

        stage('Verify Running Containers') {
            steps {
                sh 'docker compose ps'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
