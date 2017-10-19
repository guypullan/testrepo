#!/usr/bin/env groovy

pipeline {
  agent none
  options {
    timeout(time: 1, unit: 'HOURS')
    timestamps ()
    buildDiscarder(logRotator(numToKeepStr: '8'))
  }
  parameters {
    choice(name: 'BUILDTASK', choices: 'applicationdeployment\ninfrastructuredeployment\nboth', description: 'Are you working with Infrastructure, Software or both?')
    choice(name: 'FUNCTION', choices: 'stackcreation\nstackteardown\nstackupdate', description: 'What task are you wanting to perform?')
    choice(name: 'ENVIRONMENT', choices: 'int\ntest\nstage\nlive', description: 'Which environment are you building?')
    string(name: 'STACKLIST', defaultValue: 'all', description: 'which stacks are you working with?  if you want to perform work on all stacks put \"all\" in this section')
  }
  environment {
    PROJECTNAME = "testreponame"
  }
  stages {
    stage ('cosmos component creation') {
      when {
        expression { (params.BUILDTASK == 'infrastructuredeployment' || params.BUILDTASK == 'both') && params.FUNCTION != 'stackteardown' }
      }
      agent any
      steps {
        sh "echo \"hello\""
      }
    }
    stage ('stack create/delete/update') {
      when {
        expression { params.BUILDTASK == 'infrastructuredeployment' || params.BUILDTASK == 'both'}
      }
      agent any
      steps {
          sh "echo \"hello again\""
      }
    }
    
  }
}
