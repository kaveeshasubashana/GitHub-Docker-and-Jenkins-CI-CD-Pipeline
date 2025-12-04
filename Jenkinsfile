pipeline {
    agent any 
    
    stages { 
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/kaveeshasubashana/GitHub-Docker-and-Jenkins-CI-CD-Pipeline.git'
                }
            }
        }
        stage('Build Docker Image') {
            steps {  
                bat 'docker build -t kaveesha746/testnode:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'DOCKERPWD', variable: 'DOCKERPWD')]) {
                    script {
                        bat "docker login -u kaveesha746 -p %DOCKERPWD%"
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                bat 'docker push kaveesha746/testnode:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
