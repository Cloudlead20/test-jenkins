pipeline {
    
    agent any 
    
    environment {
        IMAGE_TAG = "${BUILD_NUMBER}"
        DOCKERHUB_CREDENTIALS = credentials('DOCKER_HUB')

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



             stage('Login into Docker hub'){
                 steps{
                     script{
                         sh '''
                         echo 'Buid Docker Image'
                         echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin
                         '''
                }
            }
        }

        stage('Push the dockerhub'){
            steps{
                script{
                    sh '''
                    echo 'Push'
                    docker push muthuarumugam/test-jenkins:${BUILD_NUMBER}
                    '''
                
                }
            }
        }
        
 
    }  
}

