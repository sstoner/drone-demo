pipeline {
  agent {
    kubernetes {
      label 'golang-build-${UUID.randomUUID().toString()}'
      podTemplate {
      	containerTemplate(name: "golang", image: "golang", ttyEnabled: true, command: "cat"),     
        containerTemplate(name: "busybox", image: "busybox", ttyEnabled: true, command: "cat")
      }
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
