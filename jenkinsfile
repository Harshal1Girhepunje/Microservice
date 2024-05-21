pipeline {
    agent any 

    stages {
        stage('Deploy to Kubernetes') {
            steps { 
            withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://49DA0254439755E580DE80AC880A9D9D.gr7.ap-south-1.eks.amazonaws.com']]) {
                 sh "kubectl apply -f deployment-service.yml"
                
               }
               
            }
        }
   stage('verify Deployment') {
            steps {
                echo 'withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://49DA0254439755E580DE80AC880A9D9D.gr7.ap-south-1.eks.amazonaws.com']]) {
                  sh "kubectl get svc -n webapps"
               }
            }
        }
   
    }
}
