    
pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages {
        stage('Init') {
            steps {
                echo 'Terraform init.....'
                sh 'terraform init -input=false'
            }
        }
        stage('Plan') {
            steps {
                echo 'Terraform Planning....'
                sh 'terraform plan -out=tfplan'
            }
        }
         stage('Apply'){
            steps {
                script{
                    def apply = false
                    try {
                        input message: 'confirm apply', ok: 'Apply Config'
                        apply = true
                    }
                    catch (err) {
                        apply = false
                            sh "terraform destroy -auto-approve"
                        }
                        currentBuild.result = 'UNSTABLE'
                    if(apply){
                            sh 'terraform apply tfplan'
                        }
                    }
                }
            }
        }
    }