pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello, ${MY_NAME}"
        sh 'java -version'
        echo "User: ${TEST_USER_USR}"
        echo "Pass: ${TEST_USER_PSW}"
      }
    }
  }
  environment {
    MY_NAME = 'Kyle'
    TEST_USER = credentials('test-user')
  }
}