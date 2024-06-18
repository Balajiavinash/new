pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AKIA4MTWKD7C6QGVOPEN')
        AWS_SECRET_ACCESS_KEY = credentials('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')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Balajiavinash/new.git'
            }
        }
        stage('Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Plan') {
            steps {
                sh 'terraform plan -out=tfplan'
            }
        }
        stage('Apply') {
            steps {
                sh 'terraform apply -auto-approve tfplan'
            }
        }
    }
}
