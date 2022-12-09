
pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('user check'){
      steps{
        echo"hello"
           }
    }
     stage('disk free space'){
      steps{
        sh "df -h"
           }
    }

    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
            agent{label 'slave2'}
          steps{
            echo 'action from slave2'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action from slave2 again'
          }
        }
       }
      }
    
    stage('codebuild'){
      agent {
        label {
          label 'slave3'
        }
      }
      steps{
        echo "we are done"
      }
    }
    stage('Test'){
      agent {
        label {
          label 'slave3'
        }
      }
      steps{
        echo "we have tested"
      }
    }
    }
  }

