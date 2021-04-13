#!groovy
// @Library('depa-libraries') _

stage('Get data') {
//  println getModifiedFiles()
    changedFiles = []
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
            for (file in entry.getAffectedFiles()) {
                println(changedFiles.add(file.getPath()))
            }
        }
    }
}
