pipeline {
    agent any 
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    bat "docker build -t raunak122000/2319_isa02 ."
                }
            }
        }
        stage('Delete Existing Container') {
            steps {
                script {
                    bat "docker rm -f my-app-container || exit 0"
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    bat "docker run -d --name my-app-container raunak122000/2319_isa02"
                }
            }
        }
    }
    post {
        always {
            script {
                bat "docker rmi -f raunak122000/2319_isa02 || true"
            }
        }
    }
}
