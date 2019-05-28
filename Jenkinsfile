pipeline {
  agent any
  environment {
      SECRET_IP = credentials("our_secret_ip")
  }
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
              echo "Deployed at server ${env.SECRET_IP}. Stage three completed!"
          }
      }
      stage("Four") {
          steps {
              echo "Deployed at server $SECRET_IP. Stage four completed!"
          }
      }
  }
}
