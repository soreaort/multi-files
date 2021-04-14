#!groovy
@Library(value="depa-libraries", changelog=false) _

node {
  stage('Clean Up'){
    // deleteDir()
    step([$class: 'WsCleanup'])
  }
  stage('Show results') {
    script {
    println("In the method") 
      for (changeLogSet in currentBuild.changeSets) {
         println("FOR ONE") 
         for (entry in changeLogSet.getItems()) {
           println("FOR TWO") 
           for (file in entry.getAffectedFiles()) {
              println("FOR THREE") 
              sayHello file.getPath()
              // sayHello file.getPath().split('.'[1])
            }
          }
       }
     }
  }
}
