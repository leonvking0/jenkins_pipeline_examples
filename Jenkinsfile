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
              echo "This is a credential  ${env.SECRET_IP}. You cannot see it"
              sh "curl ${env.SECRET_IP}"
          }
      }
      stage("Four") {
          steps {
              echo "This is a job parameter $SOME_PAR. Stage four completed!"
          }
      }
  }
}
