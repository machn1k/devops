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
      }
    }
    stage('Script') {
      parallel {
        stage('Script') {
          steps {
            script {
              currentBuild.displayName = "$IMF_META_FILE"
              currentBuild.description = "description."
            }

          }
        }
        stage('Another Stage') {
          steps {
            echo 'Second step after metadata stage'
          }
        }
      }
    }
  }
  environment {
    IMF_META_FILE = '${WORKSPACE}/${BUILD_TAG}'
    IMF_META_FILEJ = 'output/usefulfile.txt'
  }
}