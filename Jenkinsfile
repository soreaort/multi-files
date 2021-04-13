#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    steps {
      step([$class: 'WsCleanup'])
    }
  }
  stage('Get data') {
    steps {
      println(getModifiedFiles())
    }
  }
}
