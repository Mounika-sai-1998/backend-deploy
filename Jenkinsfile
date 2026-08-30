
pipeline {
    agent {
        label 'agent-1'
    }
    options {
        timeout( time: 1 , unit: 'HOURS' )
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'what is application version?')
    }
    environment {
        def appVersion = ''
        nexusUrl = 'nexus.lokesh.shop:8081'
    }
    stages {
        stage('print Version') {
            steps {
                script {
                    echo "application version : ${params.appVersion}"
                }
            }
        }
        stage('Init') {
            steps {
                sh """
                    cd terraform
                    terraform init
                """
            }
        }
        stage('Plan') {
            steps {
                sh """
                    pwd
                    cd terraform
                    terraform plan -var="app_version=${params.appVersion}" 
                """
            }
        }
        stage('Apply') {
            steps {
                sh """
                    cd terraform
                    terraform apply --auto-approve -var="app_version=${params.appVersion}" 
                """
            }
        }
    }
        
    post {
        always {
            echo "it will run always"
            deleteDir()
        }
        success {
            echo "it will run when the pipeline is success"
        }
         failure {
            echo "it will run when pipeline is failure"
        }
    }
    
}