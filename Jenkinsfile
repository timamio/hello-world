pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  
  stages {
    stage('Attrib Checkout') {
          steps {
            sh "ifconfig"
            sh "git clone https://github.com/timamio/hello-world.git"
            dir('hello-world') {
              sh "docker build -t hello-node."
              sh "kubectl apply -f Deployment.yaml"              
              sh "kubectl apply -f Service.yaml"
          }
    }
  }
}

