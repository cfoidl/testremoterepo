pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        ws(dir: 'tmp') {
          echo 'init'
        }

        echo 'end'
      }
    }

    stage('run') {
      steps {
        sleep 60
      }
    }

    stage('clean') {
      steps {
        cleanWs(skipWhenFailed: true, disableDeferredWipeout: true, deleteDirs: true, cleanupMatrixParent: true, cleanWhenUnstable: true, cleanWhenSuccess: true, cleanWhenNotBuilt: true, cleanWhenFailure: true, cleanWhenAborted: true)
      }
    }

  }
}