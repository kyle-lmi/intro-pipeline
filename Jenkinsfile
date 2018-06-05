pipeline {
  libraries {
    lib("SharedLibs")
  }
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello, ${params.Name}"
        sh 'java -version'
        echo "User: ${TEST_USER_USR}"
        echo "Pass: ${TEST_USER_PSW}"
      }
    }
    stage('Checkpoint') {
      steps {
        checkpoint 'Checkpoint'
      }
    }
    stage('Shared Lib') {
         steps {
             helloWorld("Jenkins")
         }
      }
  }
  environment {
    MY_NAME = 'Kyle'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'

    }

    always {
      echo "My build number is ${env.BUILD_NUMBER}"

    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
