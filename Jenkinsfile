pipeline {
    agent any

    stages {
        stage('Pull SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/git-legion/jenkins-mini-project.git'
            }
        }
        stage('Creating image') {
            steps {
                sh 'sudo docker build -t legion:v1 .'
            }
        }
        stage('Check images') {
            steps {
                sh 'sudo docker images'
            }
        }
        stage('remove container') {
            steps {
                sh 'sudo docker rm -f mycontainer3'
            }
        }
        stage('create container') {
            steps {
                sh 'sudo docker run -itd --name mycontainer3 -p 8092:80 legion:v1'
            }
        }
    }
}
