pipeline {
         agent {
                label 'pipeline_demo'
               }
         stages {
                 stage('Build') {
                                steps {
                                    sh 'echo "building your app!" > test.txt'
                                }
                 }
                 stage('Test') {
                                steps {
                                    sh 'echo "testing your app!" > test.txt'
                                }
                 }
                 stage('Deploy') {
                                  steps {
                                        sh 'echo "deploying your app!" > test.txt'
                                  }
                 }
              }
         post {
              always {
                    archiveArtifacts artifacts: 'test.txt', onlyIfSuccessful: true
              }
              success {
                   echo 'I will only get executed of this success'
              }
              failure {
                   echo 'I will only get executed if this fails'
              }
              unstable {
                   echo 'I will only get executed if this is unstable'
              }
         }
}