pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  
  stages {
    stage('CloneDeploy') {
          steps {
          dir('hello-node') {
              git branch: "master", url: "https://github.com/timamio/hello-world.git"
              sh "docker build -t hello-node ."
              sh "kubectl apply -f Deployment.yaml"              
              sh "kubectl apply -f Service.yaml"
            }  
          }
    }
  }
}

