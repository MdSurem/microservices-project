pipeline {
    agent any

    stages {
        stage('deploy') {
            steps {
                script{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-id', namespace: 'webapp', serverUrl: 'https://F9B60CE3179FD9E2DD91D6F9843A2F19.gr7.us-east-1.eks.amazonaws.com']]) {
                      sh "kubectl create -f deployment-service.yml"
                  }
                }
            }
        }
        stage('push') {
            steps {
                script{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-id', namespace: 'webapp', serverUrl: 'https://F9B60CE3179FD9E2DD91D6F9843A2F19.gr7.us-east-1.eks.amazonaws.com']]) {
                      sh "kubectl get svc -n webapp"
                  }
                }
            }
        }
    }
}
