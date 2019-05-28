pipeline {
  agent any
  stages {
      stage("One") {
          steps {
              echo "Hi, this is stage one."
          }
      }
      stage("Two") {
          steps {
              input("Test stage passed, do you want to proceed?")
          }
      }
      stage("Three") {
          steps {
              echo "Stage three completed!"
          }
      }
  }
}
