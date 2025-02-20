pipeline {
    agent any

    stages {
        stage('deploy') {
            steps {
                script{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-2', contextName: '', credentialsId: 'k8-id', namespace: 'webapps', serverUrl: 'https://FED1016C52E393D078381C3D10FE8678.yl4.us-east-1.eks.amazonaws.com']]) {
                      sh "kubectl create -f deployment-service.yml"
                  }
                }
            }
        }
        stage('push') {
            steps {
                script{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-2', contextName: '', credentialsId: 'k8-id', namespace: 'webapps', serverUrl: 'https://FED1016C52E393D078381C3D10FE8678.yl4.us-east-1.eks.amazonaws.com']]) {
                      sh "kubectl get svc -n webapp"
                  }
                }
            }
        }
    }
}
