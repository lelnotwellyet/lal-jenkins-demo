pipeline {
    agent any

    environment {
        PATH = "C:\\Users\\lalmo\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin;${env.PATH}"
    }

    stages {
        stage('build image') {
            steps {
                echo 'Building the Docker image...'
                bat 'docker build -t lal-jenkins-demo-image .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Starting the container...'
                bat 'docker rm -f lal-jenkins-demo-container || exit 0'
                bat 'docker run -d --name lal-jenkins-demo-container -p 8081:80 lal-jenkins-demo-image'
            }
        }
    }
}
