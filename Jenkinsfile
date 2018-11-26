def label = "mypod-${UUID.randomUUID().toString()}"
podTemplate(label: label) {
    node('my-jenkins-jenkins-slave') {
        stage('Run shell') {
            sh 'echo hello world'
        }
    }
}
