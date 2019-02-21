pipeline {
  agent any
  stages {
    stage('Metadata') {
      agent any
      environment {
        TEST = 'TEST_VALUE'
      }
      steps {
        echo 'Another test pipeline'
      }
    }
  }
}