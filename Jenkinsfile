pipeline {
  agent any
  stages {
    stage('S0.1') {
      agent any
      environment {
        IMF_META_FILE = '${WORKSPACE}/${BUILD_TAG}'
      }
      steps {
        echo '${WORKSPACE}/${BUILD_TAG}'
      }
    }
  }
  environment {
    IMF_META_FILE = '"${WORKSPACE}/${BUILD_TAG}"'
  }
}