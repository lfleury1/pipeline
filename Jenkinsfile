pipeline {
  agent any
  stages {
    stage('MyGroup') {
      parallel {
        stage('IMASCONV') {
          steps {
            echo 'Starting conversion of rawdata to IMAS format'
            catchError() {
              sh 'echo "Hello!"'
            }
            
          }
        }
        stage('') {
          steps {
            pwd(tmp: true)
            isUnix()
          }
        }
      }
    }
    stage('Sending mail') {
      steps {
        mail(body: 'IMASCONV has ended', subject: 'IMASCONV', to: 'ludovic.fleury@cea.fr', replyTo: 'no-reply')
      }
    }
  }
}