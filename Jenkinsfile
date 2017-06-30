#!groovy

node {
      git poll : true, url: 'https://github.com/guypullan/testrepo.git'
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
