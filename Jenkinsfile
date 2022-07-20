pipeline {
  agent any

  stages {
    stage("Build docker image") {
      steps {
        script {
          docker build --build-arg BUILD_DATE=$(date -u +'%Y-%m-%dT%H:%M:%SZ') -t dcc-cicd:latest .
        }
      }
    }

    stage("Push to dockerhub") {
      steps {
        script {
          docker push malcak/dcc-cicd:latest
        }
      }
    }
  }
}