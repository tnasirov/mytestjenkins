    
pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages {
        stage('Init') {
            steps {
                sh 'echo $AWS_ACCESS_KEY_ID'
                echo 'Terraform init.....'
                sh 'terraform init'
            }
        }
        stage('Plan') {
            steps {
                echo 'Terraform Planning....'
                sh 'terraform plan'
            }
        }
    }
}
