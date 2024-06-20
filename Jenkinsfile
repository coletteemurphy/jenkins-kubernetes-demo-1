pipeline{
    agent any
    environment{
        VERSION = "V1"
        
    }
    stages{
        stage('Deploy backend services to kubernetes cluster'){
            steps{
                sh "kubectl apply -f backend.yaml"
                }     
        }
        stage('Deploy frontend services to kubernetes cluster'){
            steps{
                sh "kubectl apply -f frontend.yaml"
                sh "kubectl get svc -w"
                sh "kubectl get svc frontend"
                }     
        }
    }
}