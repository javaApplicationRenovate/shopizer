pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                println "Build WORKSPACE ${WORKSPACE}"
                sh '''
                ls -al && pwd
                ./mvnw clean package 
                docker build -t "shopizer-main:latest" .
                docker images
                '''
            }
        }
    }
}
