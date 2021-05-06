podTemplate(label: 'veracode-example-builder', // See 1
  containers: [
    containerTemplate(
      name: 'jnlp',
      image: 'jenkinsci/jnlp-slave:3.10-1-alpine',
      args: '${computer.jnlpmac} ${computer.name}'
    ),
    containerTemplate(
      name: 'gradle',
      image: 'gradle:6.7-jdk11',
      command: 'cat',
      ttyEnabled: true
    ),
  ]
)
{
  node ('veracode-example-builder') {

    stage ('gradle version') { // See 4
      container('gradle') {
        sh '
            gradle --version
        '
      }
    }
  }
}
