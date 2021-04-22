    
pipeline {
    agent any
    stages {
        stage('Init and plan') {
            steps {
                dir ('Terraform') {
                    echo 'Terraform init.....'
                    sh 'terraform init'
                    sh 'terraform plan'
                }
            }
        }
        stage('Plan') {
            steps {
                sh 'echo $(pwd)'
                sh 'Terraform Plan....'
                sh 'terraform plan'
            }
        }
    }
}
