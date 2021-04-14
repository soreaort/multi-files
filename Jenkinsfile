#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    // deleteDir()
    step([$class: 'WsCleanup'])
  }
    stage('test advance script') {
            echo "current build number: ${currentBuild.number}"
            echo "previous build number: ${currentBuild.previousBuild.getNumber()}"
            def causes = currentBuild.rawBuild.getCauses()
            echo "causes: ${causes}"
            def rebuildCause0 = currentBuild.rawBuild.getCause(com.sonyericsson.rebuild.RebuildCause)
            echo "rebuildCause0: ${rebuildCause0}"
            echo "rebuild up number: ${rebuildCause0.getUpstreamBuild()}"
        }
  stage('Show results') {
    getChangedFiles()
  }
}

@NonCPS
def getChangedFiles() {
  def fileList = []
//  for (changeLogSet in currentBuild.changeSets) {
  println(build.currentChangesets)
  for (changeLogSet in build.currentChangesets) {
    for (entry in changeLogSet.getItems()) {
      for (file in entry.getAffectedFiles()) {
        fileList.add(file.getPath())
      }
    }
  }
  return fileList
}
