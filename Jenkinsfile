#!groovy
@Library(value="depa-libraries", changelog=false) _
// @Library("depa-libraries") _

node {
  stage('Clean Up'){
    // deleteDir()
    step([$class: 'WsCleanup'])
  }
  // Mark the code checkout 'stage'
  stage ('Checkout') {
      // Get the code from the repository
      checkout scm
  }
  stage ('Details') {
    println(env.BRANCH_NAME)
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
