pipeline {
  agent any 
    
    environment {
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps {
                 git credentialsId: 'JENKIN_GITHUB_TOKEN', 
                 url: 'https://github.com/Cloudlead20/test-jenkins',
                 branch: 'master'
            }
        }

        // stage('Build and Test') {
        //     steps {
        //         script {
        //             sh 'npm install'
        //             sh 'npm test'
        //         }
        //     }
        // }

        stage('Build Docker Image') {
            steps {
                script {
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t test-jenkins/cicd-e2e:${BUILD_NUMBER} .
                    '''
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'DOCKER_HUB') {
                    echo 'Push to Repo'
                    docker push test-jenkins/cicd-e2e:${BUILD_NUMBER}
                    ...
                    }
                }
            }
        }
    }
} }
