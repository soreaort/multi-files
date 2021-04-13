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
      println getModifiedFiles
    }
  }
}
}
