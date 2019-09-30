pipeline {
  agent { label 'minikube' }
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  
  stages {
    stage('Attrib Checkout') {
          steps {
            sh "ifconfig"
            sh "git clone https://github.com/timamio/hello-world.git"
          }
    }

  }
}
