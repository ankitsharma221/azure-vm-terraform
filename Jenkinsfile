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


{
  "environmentName": "AzureCloud",
  "homeTenantId": "fcf67057-50c9-4ad4-98f3-ffca64add9e9",
  "id": "28569ab9-06a8-483c-8cef-9fd3c9c650c7",
  "isDefault": true,
  "managedByTenants": [],
  "name": "Azure subscription 1",
  "state": "Enabled",
  "tenantDefaultDomain": "ibm.onmicrosoft.com",
  "tenantDisplayName": "IBM",
  "tenantId": "fcf67057-50c9-4ad4-98f3-ffca64add9e9",
  "user": {
    "name": "Ankit.Sharma47@ibm.com",
    "type": "user"
  }
}
