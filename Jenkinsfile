pipeline {
  agent any

  stages {
    stage("Build docker image") {
      steps {
        script {
          docker build -t "dcc-cicd:latest" .
        }
      }
    }

    stage("Push to dockerhub") {
      steps {
        script {
          docker push "malcak/dcc-cicd:latest"
        }
      }
    }
  }
}