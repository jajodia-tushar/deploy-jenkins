pipeline {
    environment {
        registry = "jajodiatushar/react-app"
        registryCredential = 'dockerhub_id'
    }
    agent any
    stages {
        stage('Building image') {
            steps{
                script {
                   dockerImage =  docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }   
        stage('Deploy Image') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                    dockerImage.push()
                    }
                }
            }
        }
    }
}