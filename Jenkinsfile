def label = "my-jenkins-jenkins-slave"
podTemplate(label: label) {
    node(label) {  
        stage('Run shell') {
            container('jnlp') {
                 sh 'echo hello world'
            }
        }
    }
}
