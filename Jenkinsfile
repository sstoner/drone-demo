def label = "my-label"
podTemplate(label: label) {
    node(label) {  
        stage('Run shell') {
           container('mycontainer') {
                sh 'echo hello world'
              }
        }
    }
}
