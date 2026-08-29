
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
        nexusUrl = '32.197.164.123:8081'
    }
    stages {
        stage('print Version') {
            steps {
                script {
                    echo "application version : ${params.appVersion}"
                }
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