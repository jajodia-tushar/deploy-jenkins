pipeline {
    agent any 

    stages {
        stage('Build Assets') {
            agent any 
            steps {
                sh 'echo "Building Docker Image"'
                sh 'docker build -t jajodiatushar/react-app .'
            }
        }
        stage('Test') {
            agent any
            steps {
                sh 'echo "Pushing Docker to DockerHub"'
                sh 'docker push jajodiatushar/react-app'
            }
        }
    }
}