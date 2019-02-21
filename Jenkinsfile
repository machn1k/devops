pipeline {
  agent any
  stages {
    stage('Metadata') {
      agent any
      environment {
        TEST1 = '${WORKSPACE}'
        TEST2 = '${env.WORKSPACE}'
      }
      steps {
        echo 'Another test pipeline $IMF_META_FILE'
        script {
          currentBuild.displayName = "$IMF_META_FILE"
          currentBuild.description = "Sample Description"
        }

        echo 'Variable TEST1: "${env.TEST1}" $TEST1'
        echo 'Variable TEST2: "$TEST2"'
      }
    }
    stage('Step 2') {
      parallel {
        stage('Script') {
          steps {
            echo '$IMF_META_FILE'
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
  environment {
    IMF_META_FILE = '"${WORKSPACE}/${BUILD_TAG}"'
  }
}