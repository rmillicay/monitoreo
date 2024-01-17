pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''echo \'Construccion\'
docker run -d -p 80:80 --name web nginx:latest'''
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'sleep 10'
          }
        }

        stage('Test 2') {
          steps {
            sh '''echo "Test 2"
sleep 5'''
          }
        }

      }
    }

    stage('Destroy') {
      steps {
        sh 'docker stop web && docker rm web'
      }
    }

  }
}