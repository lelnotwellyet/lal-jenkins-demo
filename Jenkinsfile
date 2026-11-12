pipeline{
  agent any
  stages{
    stage('build image'){
      steps{
        bat 'docker build -t lal-jenkins-demo-image .'
      }
    }
    stage('Run Docker Container'){
      steps{
        bat 'docker run -d --name lal-jenkins-demo-container -p 8081:80 lal-jenkins-demo-image'
      }
    }
  }
}
