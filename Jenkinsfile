pipeline {
  agent any
  stages {
    stage('Build Image') {
      steps {
        sh 'docker build -t malcak/dcc-cicd:latest .'
      }
    }

    stage('Login DockerHub') {
      steps {
        sh 'echo $dockerhub_pw | docker login -u $dockerhub_user --password-stdin'
      }
    }

    stage('Push Image') {
      steps {
        sh 'docker push malcak/dcc-cicd:latest'
      }
    }

    stage('Logout Dockerhub') {
      steps {
        sh 'docker logout'
      }
    }

  }
}