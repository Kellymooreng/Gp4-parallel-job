
pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('user check'){
      steps{
        sh 'cat/etc/passwd'
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
        stage('sub-job3'){
            steps{
                echo 'action3'
            }
        }
      }
    }
    stage('codebuild'){
      agent {
        label {
          label 'slave1'
        }
      }
      steps{
        sh 'cat /etc/passwd'
      }
    }
  }
}
