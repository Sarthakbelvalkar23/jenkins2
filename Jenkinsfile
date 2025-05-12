pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'flask-jenkins-ci-cd'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                script {
                    docker.build(DOCKER_IMAGE)
                }
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                // Optionally, add test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
                sh 'docker run -d -p 5000:5000 flask-jenkins-ci-cd'
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
