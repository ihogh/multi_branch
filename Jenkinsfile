pipeline{
  agent any
  stages{
    stage('git-clone'){
      steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/ihogh/multi_branch.git']]])
      }
    }
    stage('1-first parallel job'){
      parallel{
        stage('Phil-actions'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/jenkins_parallel/phil_jkp.sh'
                      }
        }
        stage('Abisola-actions2'){
          steps{
            sh 'echo "thank you"'
          }
        }
      }
    }

    stage('2-second parallel job'){
      parallel{
        stage('Engr-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
        stage('engr2-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
      }
    }
    stage('3-third parallel job'){
      parallel{
        stage('engr1-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
        stage('engr2-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
      }
    }
    stage('4-fourth parallel job'){
      parallel{
        stage('engr1-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
        stage('engr2-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
      }
    }
    stage('5-fifth parallel job'){
      parallel{
        stage('engr1-action'){
          steps{
            sh 'echo "thank you"'
          }
        }
        stage('engr2-action'){
          steps{
            sh 'echo "thank you"'
            sh 'echo "Testing muti-branching"'
          }
        }
      }
    }
  }
}
