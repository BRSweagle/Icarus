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

        stage('CodePush') {
          steps {
            echo 'Code changes'
          }
        }

      }
    }

    stage('Testing') {
      parallel {
        stage('Testing') {
          steps {
            sleep(time: 2, unit: 'SECONDS')
            echo 'Testing Started'
          }
        }

        stage('Performance') {
          steps {
            echo 'Environments being provisioned'
            echo 'Complete.'
          }
        }

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
