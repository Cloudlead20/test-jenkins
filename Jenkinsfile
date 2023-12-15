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
                    sh '''
                    echo 'Push to Repo'
                    docker push muthuarumugam/test-jenkins:${BUILD_NUMBER}
                    '''
                }
            }
        }
        
 
        

    }
}
