#!groovy

node (blah) {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage ('usingparallel') {
          steps {
            echo 'parallelprocess1'
          }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
          input 'should i deploy this code?'
            steps {
                echo 'Deploying....'
            }
        }
}
