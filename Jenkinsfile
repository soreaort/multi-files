#!groovy
// @Library(value="depa-libraries", changelog=false) _
@Library("depa-libraries") _

node {
  stage('Clean Up'){
    // deleteDir()
    step([$class: 'WsCleanup'])
  }
  getChangedFiles()
}

@NonCPS
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
