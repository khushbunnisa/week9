pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 khushbunnisashaik/registration:v1'
                bat 'docker push khushbunnisashaik/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/Admin/Downloads/Week-2/week9/deployment.yaml'
                bat 'kubectl apply -f C:/Users/Admin/Downloads/Week-2/week9/service.yaml'
            }
        }
    }
}
