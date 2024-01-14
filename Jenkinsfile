pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/erbolat9090/cicd-pipeline.git', branch: 'main')
      }
    }

    stage('Build App') {
      steps {
        sh 'script scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        sh 'script scripts/test.sh'
      }
    }

    stage('Build a docker image') {
      steps {
        sh '''docker build -t yerbolattileutay/jenkins_cicd_test_image:$BUILD_NUMBER .

'''
      }
    }

  }
}