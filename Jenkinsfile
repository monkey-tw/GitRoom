pipeline {
  agent any
  stages {
    stage('Hello') {
      steps {
        echo 'Hello World'
      }
    }

    stage('clean') {
      steps {
        echo 'clean ok'
      }
    }

    stage('post') {
      steps {
        sh 'echo "post"'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }

  }
  environment {
    GITROOM_NAME = 'haha'
    GITROOM_AGE = '33'
  }
}