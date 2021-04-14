#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    // deleteDir()
    step([$class: 'WsCleanup'])
  }
  stage('Show results') {
    script {
      getChangedFiles()
    }
  }
}

@NonCPS
def getChangedFiles() {
//  fileList = []
  for (changeLogSet in currentBuild.changeSets) {
    for (entry in changeLogSet.getItems()) {
      for (file in entry.getAffectedFiles()) {
         sayHello file.getPath()
       }
     }
  }
//  return fileList
}
