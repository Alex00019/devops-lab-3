pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeConfig(
                    credentialsId: 'kubernetes-creds',
                    serverUrl: '',
                    namespace: 'demo'
                ) {
                    sh 'helm upgrade --install demo microservices/msvc-chart --namespace demo'
                }
            }
        }
    }
}
