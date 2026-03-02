pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeConfig([
                    credentialsId: 'kubernetes-creds',
                    serverUrl: 'https://172.19.32.1:38573',
                    namespace: 'demo'
                ]) {
                    sh 'helm upgrade --install demo microservices/msvc-chart --namespace demo'
                }
            }
        }
    }
}
