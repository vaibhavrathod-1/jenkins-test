pipeline {
    agent any
    environment {
        IMAGE='vaibhavrathod/jenkins-test'
        TAG='latest'
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build --pull -t ${IMAGE}:${TAG} ."
            }
        }
        stage('Push to dockerhub') {
         
            steps {
                // withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'dockerPassword', usernameVariable: 'dockerUsername')]) {
                    sh "docker login -u vaibhavrathod -p zerov@09876"
                    sh "docker push ${IMAGE}:${TAG}"
                }
            }
        }
    }
vaibhav rathod hello what r u doing
