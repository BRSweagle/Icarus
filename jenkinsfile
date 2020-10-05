pipeline {
  agent any
  stages {
    stage('Git') {
      parallel {
        stage('Git') {
          steps {
            git(url: 'https://github.com/BRSweagle/Icarus', poll: true)
          }
        }

    stage('Config') {
      parallel {
        stage('Config') {
          steps {
            SWEAGLEUpload(actionName: 'uploadConfig', fileLocation: '/Components/Files', format: 'properties', nodePath: 'Icarus,Components,Files', subDirectories: true, tag: '${BUILD_ID)', autoRecognize: true, withSnapshot: false)
          }
        }

    stage('Deployment') {
      parallel {
        stage('Deployment') {
          steps {
            echo 'Push to TST'
          }
        }

        stage('TestEnv1') {
          steps {
            echo 'Deployed'
          }
        }

      }
    }

  }
}
}
}
}
