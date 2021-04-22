  
pipeline {
    agent any
    stages {
        stage('Init and plan') {
            steps {
                sh 'cd Terraform'
                echo 'Terraform init.....'
                sh 'terraform init'
            }
        }
        stage('Plan') {
            steps {
                sh 'Terraform Plan....'
                sh 'terraform plan'
            }
        }
    }
}