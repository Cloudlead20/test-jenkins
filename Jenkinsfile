credentials {
    id 'DOCKER_HUB'
}

pipeline {
    
    agent any 
    
    environment {
        IMAGE_TAG = "${BUILD_NUMBER}"
    }
    
    stages {
        
        stage('Checkout'){
           steps {
                git credentialsId: 'JENKIN_GITHUB_TOKEN', 
                url: 'https://github.com/Cloudlead20/test-jenkins',
                branch: 'master'
           }
        }

        stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t muthuarumugam/test-jenkins:${BUILD_NUMBER} .
                    '''
                }
            }
        }

        stage('Push the dockerhub'){
           steps{
                script{
                    //Authenticate with Docker registry using credentials
                    withCredentials([usernamePassword(credentialsId: DOCKER_HUB, usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    // Build and push Docker image
                    // sh "docker build -t $DOCKER_REGISTRY/$DOCKER_IMAGE:latest ."
                    sh "docker login -u muthuarumugam/test-jenkins:${BUILD_NUMBER}"
                    sh "docker push muthuarumugam/test-jenkins:${BUILD_NUMBER}"
                }
            }
        }
        
 
        

    }
}
