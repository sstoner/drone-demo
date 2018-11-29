pipeline {
  agent {
    kubernetes {
      label 'golang-build'
      containerTemplate {
        name 'golang'
        image 'golang'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  environment {
    CONTAINER_ENV_VAR = 'container-env-var-value'
  }
  stages {
    stage('Run golang') {
      steps {
        sh 'set'
        sh "echo OUTSIDE_CONTAINER_ENV_VAR = ${CONTAINER_ENV_VAR}"
        container('golang') {
          sh 'go version'
          sh 'uname -a'
        }
      }
    }
	stage('Run maven with a different shell') {
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
