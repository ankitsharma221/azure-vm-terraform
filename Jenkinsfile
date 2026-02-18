pipeline {
    agent any

    tools {
        terraform 'terraform'   // Refers to the Terraform tool you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Explicit Git checkout from your repo
                git branch: 'main', url: 'https://github.com/ankitsharma221/azure-vm-terraform.git'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -out=tfplan'
            }
        }

        stage('Terraform Apply') {
            steps {
                input message: "Approve to apply Terraform changes?"
                sh 'terraform apply tfplan'
            }
        }
    }
}
