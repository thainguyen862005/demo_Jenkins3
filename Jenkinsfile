pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Get source code'
      }
    }

    stage('Build') {
      steps {
        echo 'Compile project'
      }
    }

    stage('Test') {
      steps {
        error 'Test failed on purpose'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy to server/container'
      }
    }

  }
}
