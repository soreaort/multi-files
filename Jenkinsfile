#!groovy
@Library(value="depa-libraries", changelog=false) _

pipeline {
agent any
stages {
  stage('Clean Up'){
    steps {
      step([$class: 'WsCleanup'])
    }
  }
  stage('Get data') {
    steps {
      script {
            for (changeLogSet in currentBuild.changeSets) {
              for (entry in changeLogSet.getItems()) {
                for (file in entry.getAffectedFiles()) {
                  // sayHello file.getPath()
                  sayHello file.getPath().getMethods()
                }
              }
            }
      }
    }
  }
}
}
