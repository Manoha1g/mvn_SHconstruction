#!groovy
//@Library('sharedlibraries@master')
//import os_directoryMake

pipeline{
  agent any
  environment {
    OUT_DIR = "${env.WORKSPACE}/out"
  }
  tools { 
    maven 'maven-3.6.1' 
  }
  stages{
    stage ('creating a directory') {
      steps {
        echo "Creating a directory"
//        os_directoryMake ("${OUT_DIR}")
      }
    }
  }
}
