#!groovy

pipeline {
    agent any

    stages {
      node (blah) {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
      }
      node (blah) {
        stage ('usingparallel') {
          steps {
            echo 'parallelprocess1'
          }
        }
      }
      node (blah) {
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
      }
      node (blah) {
        stage('Deploy') {
          input 'should i deploy this code?'
            steps {
                echo 'Deploying....'
            }
        }
      }
    }
}
