pipeline {
  agent any
  stages {
    stage('clone repository') {
      steps {
        echo 'Clone repository'
      }
    }

    stage('Deploy billing App') {
      steps {
        withCredentials(bindings: [
                      string(credentialsId: 'kubernete-jenkis-server-account', variable: 'api_token')
                      ]) {
            sh 'kubectl --token $api_token --server https://192.168.49.2:8443 --insecure-skip-tls-verify=true apply -f deployment-mytools-app.yaml '
          }

        }
      }

    }
  }
