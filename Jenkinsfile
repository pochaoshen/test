podTemplate(
    name: "pod template",
    containers: [containerTemplate(name: 'ctn', image: 'jenkins/inbound-agent', ttyEnabled: true, command: 'cat')],
) {
    node("test") {
        stage("1") {
            container("ctn") {
                sh "echo stage 1"
            }
        }
        
        stage("1") {
            container("ctn") {
                sh "echo stage 2"
            }
        }
    }
}
