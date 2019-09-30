pipeline {
  agent { label 'minikube' }
  
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  parameters {
        choice(
        name: 'BRNCH',
        choices: "develop\nmaster",
        description: 'Select branch for hello world deployemnt' 
        )
    }

  stages {
    stage('Attrib Checkout') {
          steps {
            git branch: "${params.BRNCH}", changelog: false,  poll: false, url: "https://github.com/timamio/${params.URL}"
            sh "ls -larth"
          }
    }

  }
}
