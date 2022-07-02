// pipeline {
//     agent any
//     tools {
//         terraform 'terraform'
//     }
//     stages {
//         stage('Git Init') {
//             steps {
//                 git credentialsId: 'your_token', url: 'https://github.com/777leyla/GoGrTeam3.git'
//             }
//         }
//         stage('Terraform Init') {
//             steps {
//                 sh 'terraform init -no-color'
//             }
//         }
//         stage('Terraform Plan') {
//             steps {
//                 sh 'terraform plan -no-color' 
//             }
//         }
//         stage('Terraform Apply') {
//             steps {
//                 sh 'terraform apply --auto-approve -no-color' 
//             }
//         }
//     }
// }

pipeline {
    agent any
    tools {
        terraform 'terraform'
    }
    stages {
        stage('Git init') {
            steps {
                git credentialsId: 'your_token', url: 'https://github.com/777leyla/GoGrTeam3.git'
            }
        }
        stage('Terraform init') {
            steps {
                sh 'terraform init -no-color'
            }
        }
        stage('Terraform plan') {
            steps {
                sh 'terraform plan -destroy -no-color'
            }
        }
        stage('Terraform Destroy') {
            input {
                message "Do you want to destroy deployment?"
            }
            steps {
                sh 'terraform destroy --auto-approve -no-color'
            }
        }
    }
}