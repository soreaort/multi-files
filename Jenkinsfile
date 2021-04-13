#!groovy
@Library('depa-libraries') _

stage('Get data') {
//  println getModifiedFiles()

println(currentBuild.changeSets) // should print an empty set

checkout(scm)

println(currentBuild.changeSets) // should print out any changes in the current build
}
