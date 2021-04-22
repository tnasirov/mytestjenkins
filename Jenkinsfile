  
pipeline {
    agent any
    stages {
        stage('Init and plan') {
            steps {
                sh 'echo $(pwd)'
                sh 'terraform init'
                sh 'terraform plan'
            }
        }
    }
}