podTemplate(
    label: "my-label",
    name: "pod template",
    namespace: "cicd",
    containers: [containerTemplate(name: 'ctn', image: 'jenkins/inbound-agent:4.7-1-jdk11', ttyEnabled: true, command: 'cat')],
    volumes: [
        hostPathVolume(
            mountPath: '/var/run/docker.sock',
            hostPath: '/var/run/docker.sock'
        ),
    ],
    ports: ["8080", "50000"]
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
