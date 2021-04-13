node {
  stage('Get data') {
    changedFiles = []
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
            for (file in entry.getAffectedFiles()) {
                // changedFiles.add(file.getPath())
                println(file.getPath())
            }
        }
    }
  }
}
