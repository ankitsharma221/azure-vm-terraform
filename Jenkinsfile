pipeline {
    agent any

    tools {
        terraform 'terraform'   // Refers to the Terraform tool you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from GitHub
                checkout scm
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
