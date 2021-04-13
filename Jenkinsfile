#!groovy
// @Library('depa-libraries') _

stage('Get data') {
//  println getModifiedFiles()
    print("it works")
    changedFiles = []
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
            for (file in entry.getAffectedFiles()) {
                changedFiles.add(changedFiles.add(file.getPath()))
            }
        }
    }
  print(changedFiles)
}
