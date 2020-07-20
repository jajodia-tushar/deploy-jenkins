pipeline {
    agent any 

    stages {
        stage('Build Assets') {
            agent any 
            steps {
                docker build -t jajodiatushar/react-app .
            }
        }
        stage('Test') {
            agent any
            steps {
                docker push jajodiatushar/react-app
            }
        }
    }
}