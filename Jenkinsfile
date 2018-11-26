pipeline {
  agent {
podTemplate(inheritFrom: 'default-slave', instanceCap: 0, label: 'my-jenkins-jenkins-slave ', name: '', namespace: 'default', nodeSelector: '', podRetention: always(), serviceAccount: '', workspaceVolume: emptyDirWorkspaceVolume(false)) {

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
