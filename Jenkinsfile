pipeline {
  agent any
  environment {
    DOCKER_CREDENTIALS = credentials('dockerhub-credentials')
  }

  stages {
    stage('Build Image') {
      steps {
        sh 'docker build -t malcak/dcc-cicd:latest .'
      }
    }

    stage('Login DockerHub') {
      
      steps {
        sh 'echo $DOCKER_CREDENTIALS_PSW | docker login -u $DOCKER_CREDENTIALS_USR --password-stdin'
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