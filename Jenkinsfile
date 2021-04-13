pipeline {
  agent any
  triggers {
    pollSCM('* * * * *')
   }
  stages {
    stage('Get modified files') {
      steps {
        script {
          def getChangedFilesList() {
            changedFiles = []
            for (changeLogSet in currentBuild.changeSets) {
              for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
                for (file in entry.getAffectedFiles()) {
                  changedFiles.add(file.getPath()) // add changed file to list
                }
              }
            }
          return changedFiles
          }
        }
      }
    }
    stage('Print modified files') {
      steps {
        echo 'Building..'
      }
    }
  } 
}
