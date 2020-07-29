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
        stage('Deploy Image to DockerHub') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                    dockerImage.push()
                    }
                }
            }
        }
        stage('Remove docker Image From Local') {
            steps{
                sh "docker rmi $registry:$BUILD_NUMBER"
            }
        }  
    }
}