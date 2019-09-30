pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  
  stages {
    stage('Attrib Checkout') {
          steps {
            sh "ifconfig"
            sh "cd hello-world && git clone https://github.com/timamio/hello-world.git"
            sh "cd hello-world && docker build -t hello-node ."
            sh "cd hello-world && kubectl apply -f Deployment.yaml"              
            sh "cd hello world && kubectl apply -f Service.yaml"
          }
    }
  }
}

