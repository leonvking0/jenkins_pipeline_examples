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
     stage('Failure Test') {
         steps {
             sh 'echo "Fail!"; exit 1'
         }
     }
  }
     post {
         always {
             echo 'This will always run'
         }
         success {
             echo 'This will run only if successful'
         }
         failure {
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "foo@foomail.com";
         }
         unstable {
             echo 'This will run only if the run was marked as unstable'
         }
         changed {
             echo 'This will run only if the state of the Pipeline has changed'
             echo 'For example, if the Pipeline was previously failing but is now successful'
         }
     }
}
