pipeline {
    agent any
    environment {
        TF_VAR_credentials = credentials('aws-jenkins')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/binank/vmterraform.git'
            }
        }
        stage('Build Infrastructure') {
            steps {
                withAWS(credentials: '112') {
                   // sh 'terraform init'
                    sh 'terraform apply -auto-approve'
                }
            }
        }
        stage('Deploy Infrastructure') {
            steps {
                sh 'echo "Infrastructure built successfully"'
            }
        }
        stage('Deployment success') {
            steps {
                sh 'echo "Infra_deployment successfully completed"'
            }
        }
    }
}
