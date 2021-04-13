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
  stage('Test'){
    steps {
      sayHello 'Alex3'
    }
  }
  stage('Get data') {
    steps {
      script {
            for (changeLogSet in currentBuild.changeSets) {
              for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
                for (file in entry.getAffectedFiles()) {
                  // println file.getPath()
                   println file
                }
              }
            }
      }
    }
  }
}
}
