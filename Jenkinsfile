pipeline {
  agent any
  stages {
      stage("One") {
          steps {
              echo "Hi, this is stage one. We are at build number: ${env.BUILD_NUMBER}"
          }
      }
      stage("Two") {
          steps {
              input("Test stage passed, do you want to proceed?")
          }
      }
      stage("Three") {
          steps {
              echo "Deployed at server ${env.SOME_SECRET_IP}. Stage three completed!"
          }
      }
  }
}
