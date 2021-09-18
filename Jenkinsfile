pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        ws(dir: 'tmp') {
          echo 'init'
        }

        sleep 60
        echo 'end'
      }
    }

    stage('run') {
      steps {
        sleep 60
        sh '''echo =======
pwd
echo =======
ls -al
echo =======
cp srv.txt $HOME/runlog/srv.txt.$$
echo =======
'''
      }
    }

    stage('clean') {
      steps {
        cleanWs(skipWhenFailed: true, disableDeferredWipeout: true, deleteDirs: true, cleanupMatrixParent: true, cleanWhenUnstable: true, cleanWhenSuccess: true, cleanWhenNotBuilt: true, cleanWhenFailure: true, cleanWhenAborted: true)
      }
    }

  }
}