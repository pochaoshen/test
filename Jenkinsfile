podTemplate(
    label: "my-label",
    name: "pod template",
    namespace: "cicd",
    containers: [containerTemplate(name: 'jnlp', image: 'jenkins/inbound-agent:4.7-1-jdk11', ttyEnabled: true, command: 'cat')],
    volumes: [
        hostPathVolume(
            mountPath: '/var/run/docker.sock',
            hostPath: '/var/run/docker.sock'
        ),
    ]
) {
    node("my-label") {
        stage("1") {
            container("jnlp") {
                sh "echo stage 1"
            }
        }
    }
}
