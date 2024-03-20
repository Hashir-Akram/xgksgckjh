pipeline {
    agent any
    tools{
        maven 'Maven_3_5_0'
    }
    stages{
        stage('Build Maven'){
            steps{
                git branch: 'main', url: 'https://github.com/Hashir-Akram/xgksgckjh.git'
                bat 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    bat 'docker build -t devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                    withCredentials([string(credentialsId: 'secret_id', variable: 'dockerhubKey')]) {
                           bat 'docker login -u hashirdocker123 -p K7Tk/K$!ziPAb8C docker.io'

}
                    bat 'docker tag devops-integration:latest hashirdocker123/hashirdocker123repo:v3'
					bat 'docker 
                   bat 'docker images'
                   bat 'docker push hashirdocker123/hashirdocker123repo:v3'
                }
            }
        }
        
    }
}