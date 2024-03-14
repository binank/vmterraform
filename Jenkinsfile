pipeline {
    agent any
    environment {
        TF_VAR_credentials = credentials('aws-jenkins')
    }
    stages {
        stage('Destroy Infrastructure') {
            steps {
                withAWS(credentials: 'aws-jenkins') {
                    //sh 'terraform init'
                    sh 'terraform destroy -auto-approve'
                }
            }
        }
    }
}

