pipeline {
    agent any
    environment {
        dockerImage = ' '
        registry = 'arulvp/nodesample'
        
    }
    stages {
        stage ("git checkout") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Arulvp/nodesample.git']]])
            }
        }
        stage ("Docker Build") {
            steps {
                script {
                    dockerImage = docker.build registry
                }
            }
        }
    }
}
