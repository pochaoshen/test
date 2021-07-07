podTemplate(
    label: "my-label",
    name: "pod template",
    containers: [containerTemplate(name: 'ctn', image: 'jenkins/inbound-agent:4.9-1-jdk11-nanoserver-1809', ttyEnabled: true, command: 'cat')],
) {
    node("my-label") {
        stage("1") {
            container("ctn") {
                sh "echo stage 1"
            }
        }
        
        stage("2") {
            container("ctn") {
                sh "echo stage 2"
            }
        }
    }
}
