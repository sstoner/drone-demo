def label = "mypod-${UUID.randomUUID().toString()}"
podTemplate(label: label) {
    node('node3') {
        stage('Run shell') {
            sh 'echo hello world'
        }
    }
}
