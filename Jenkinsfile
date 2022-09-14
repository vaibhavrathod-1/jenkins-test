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
            when {
                branch 'master'
            }
            steps {
                // withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'dockerPassword', usernameVariable: 'dockerUsername')]) {
                    sh "docker login -u vaibhavrathod -p zerov@09876"
                    sh "docker push ${env.IMAGE}:${TAG}"
                }
            }
        }
    }
