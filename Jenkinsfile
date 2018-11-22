pipeline {
  agent {
    docker {
      image "golang:alpine"
    }
  }
  stages {
    stage("build") {
      steps {
        echo "Hello Builder!"
      }
    }
    
    stage("Test") {
      steps {
        echo "Hello Builder!"
      }  
    }
    
    stage("Deploy") {
      steps {
        echo "Hello Builder!"
      }
    }
 
 
 } //stages
 post {
  always {
     echo "Always Post!"
   }
 }
}
