pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''echo \'Construccion\'
docker run -p 80:80 --name web nginx:latest'''
      }
    }

    stage('Test') {
      steps {
        sh 'sleep 10'
      }
    }

    stage('Destroy') {
      steps {
        sh 'docker stop web && docker rm web'
      }
    }

  }
}