
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
<<<<<<< HEAD
        nexusUrl = 'nexus.lokesh.shop'
=======
        nexusUrl = '32.197.164.123:8081'
>>>>>>> 537848fcfff223fc6f91e280c0ca07c0ec850c52
    }
    stages {
        stage('print Version') {
            steps {
                script {
                    echo "application version : ${params.appVersion}"
                }
            }
        }
<<<<<<< HEAD
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
                    cd terraform
                    terraform plan -vars 
            }
        }
=======
>>>>>>> 537848fcfff223fc6f91e280c0ca07c0ec850c52
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