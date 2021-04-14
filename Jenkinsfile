#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    // Clean up workspace
    deleteDir()
  }
  stage('Show results') {
    for (changeLogSet in currentBuild.changeSets) {
       for (entry in changeLogSet.getItems()) {
         for (file in entry.getAffectedFiles()) {
            sayHello file.getPath()
            // sayHello file.getPath().split('.'[1])
          }
        }
     }
  }
}
