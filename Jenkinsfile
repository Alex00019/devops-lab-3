pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeConfig([credentialsId: 'kubernetes-creds']) {
                    sh 'helm upgrade --install demo microservices/msvc-chart --namespace demo'
                }
            }
        }
    }
}
