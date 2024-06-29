pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E4B984E25269CCBDB9B840B4144CE205.gr7.ap-south-1.eks.amazonaws.com']]) {
                   "kubectl apply -f deployment-service.yml" 
            
                }        
            }
        }
        
        stage('Hello') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E4B984E25269CCBDB9B840B4144CE205.gr7.ap-south-1.eks.amazonaws.com']]) {
                   sh "kubectl get svc -n webapps"
               }
            }
        }
     }
  }
