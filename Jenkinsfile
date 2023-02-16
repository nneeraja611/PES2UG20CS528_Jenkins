pipeline {
agent any
stages {
    stage('Build') {
        steps {
            sh 'g++ -o pes2ug20cs528-1 sample.cpp'
        }
    }
    
    stage('Test') {
        steps {
            sh './pes2ug20cs528-1'
        }
    }
    
    stage('Deploy') {
      when {
          sh nvm
        expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS' 
        }
      }
      steps {
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
