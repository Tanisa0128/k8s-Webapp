 pipeline {
    agent any
    stages {
        stage('Deploy to Kubernetes') {
            steps {
                echo 'Applying Kubernetes manifests...'
                sh 'kubectl apply -f webapp.yaml'
                sh 'kubectl apply -f mongo.yaml'
            }
        }
    }
}
