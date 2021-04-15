#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    step([$class: 'WsCleanup'])
  }
  stage ('Checkout') {
      checkout scm
  }
  stage ('Details') {
    rawData = ['onefile.rb','path/to/new/file.lock.json','new.rb','justone/deep.txt']
    for (data in rawData){
      if (data.contains('/'){
        println(data.split('/').last())
      } else {
        println(data)
      }
    }
    for (file in getChangedFiles()){
      awesomePipeline(fileName: file)
    }
  }
}

// Investigate what is it for
// @NonCPS
def getChangedFiles() {
  def fileList = []
  for (changeLogSet in currentBuild.changeSets) {
    for (entry in changeLogSet.getItems()) {
      for (file in entry.getAffectedFiles()) {
        fileList.add(file.getPath())
      }
    }
  }
  return fileList
}
