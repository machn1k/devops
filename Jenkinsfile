pipeline {
  agent any
  stages {
    stage('Metadata') {
      agent any
      environment {
        TEST = 'TEST_VALUE'
      }
      steps {
        echo 'Another test pipeline $IMF_META_FILE'
        script {
          currentBuild.displayName = "$IMF_META_FILE"
          currentBuild.description = "Sample Description"
        }

      }
    }
    stage('Script') {
      parallel {
        stage('Script') {
          steps {
            echo '"$IMF_META_FILE"'
          }
        }
        stage('Another Stage') {
          steps {
            echo 'Second step after metadata stage'
          }
        }
      }
    }
    stage('Cleanup') {
      steps {
        cleanWs(cleanWhenAborted: true, cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenSuccess: true, cleanWhenUnstable: true, cleanupMatrixParent: true)
        echo 'Cleanup Step'
        echo 'A third step under cleanup'
      }
    }
  }
}