pipeline {
  agent any
  stages {
    stage('S0.1') {
      agent any
      environment {
        IMF_META_FILE = '${WORKSPACE}/${BUILD_TAG}'
      }
      steps {
        echo '$IMF_META_FILE'
      }
    }
  }
  environment {
    IMF_META_FILE = '${env.WORKSPACE}'
  }
}