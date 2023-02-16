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
        
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
