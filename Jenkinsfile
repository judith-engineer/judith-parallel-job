 pipeline{
    agent any
  stages{
    stage('git clone'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/judith-engineer/judith-parallel-job.git']]])
      }
    }
  stage('parallel-level'){
    parallel{
      stage('sub-job1 judith'){
        steps{
          echo "sub-job1 task"
        }
      }
      stage('sub-job2'){
        steps{
          echo "sub-job2 task"
        }
      }
      stage('webhook'){
        steps{
           echo "just trying the 3rd line"
        }
        
      }
    }
  }
  stage('version-check'){
    steps{
      echo "end of parallel job"
    }
  }
  stage('usercheck'){
    steps{
      sh 'cat /etc/passwd | grep Jenkins'
    }
  }
  }
}

