pipeline {
  agent {
    kubernetes {
      label 'my-build-golang'
      defaultContainer "jenkinsci/jnlp-slave"
      yaml """
apiVersion: v1
kind: Pod
metadata: 
   labels: 
     run-build: golang-build
spec: 
   containers:
   - name: golang
     image: golang
     command: 
     - cat
     tty: true
   - name: busybox
     image: busybox
     command: 
     - cat 
     tty: true
      """      
    }
  }
  environment {
    CONTAINER_ENV_VAR = 'container-env-var-value'
  }
  stages {
    stage('Run golang build') {
      steps {
        sh 'set'
        sh "echo OUTSIDE_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}"
        container('golang') {
          sh 'go version'
          sh 'uname -a'
        }
      }
    }
	stage('deploy kubectl') {
		steps {
		  container(name: 'golang', shell: 'sh') {
			sh 'go version'
		  }
		  container(name: 'busybox') {
			sh 'uname -a'
		  }
		}
	  }
  }
}
