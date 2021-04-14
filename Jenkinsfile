#!groovy
@Library(value="depa-libraries", changelog=false) _

    for (changeLogSet in currentBuild.changeSets) {
       for (entry in changeLogSet.getItems()) {
         for (file in entry.getAffectedFiles()) {
            sayHello file.getPath()
            // sayHello file.getPath().split('.'[1])
          }
        }
     }
