#!groovy

node('master') {

  def utils = load "/scripts/buildUtils.groovy"

  stage ('Extract') {
    checkout scm
  }

  stage ('Build') {
    utils.mavenBuild ('clean', 'package')
    utils.dockerBuild('LibertyProject2')
  }

  stage ('Deploy') {
    utils.deploy ()
  }
}