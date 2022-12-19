pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/Srikanthreddy1000/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'sudo docker image build -t shaikkhajaibrahim/saleor-devops:DEV1.0 .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push shaikkhajaibrahim/saleor-devops:dev2.0'
            }
     }
   }
}