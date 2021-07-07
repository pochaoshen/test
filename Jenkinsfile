podTemplate(
    label: "my-label",
    name: "pod template",
    namespace: "cicd",
    containers: [containerTemplate(name: 'ctn', image: 'jenkins/inbound-agent:4.7-1-jdk11', ttyEnabled: true, command: 'cat', ports: [
        portMapping(name: 'aa', containerPort: 8080, hostPort: 8080),
        portMapping(name: 'bb', containerPort: 50000, hostPort: 50000)
    ])],
    volumes: [
        hostPathVolume(
            mountPath: '/var/run/docker.sock',
            hostPath: '/var/run/docker.sock'
        ),
    ]
) {
    node("my-label") {
        stage("1") {
            container("ctn") {
                sh "echo stage 1"
            }
        }
    }
}
