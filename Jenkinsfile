pipeline {
    agent any
    tools {
        terraform 'terraform'
    }
    stages {
        stage('Git Init') {
            steps {
                git credentialsId: 'your_token', url: 'your_repo_url'
            }
        }
        stage('Terraform Init') {
            steps {
                sh 'terraform init -no-color'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -no-color' 
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply --auto-approve -no-color' 
            }
        }
    }
}