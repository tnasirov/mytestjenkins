    
pipeline {
    agent any
    stages {
        stage('Init and plan') {
            steps {
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
