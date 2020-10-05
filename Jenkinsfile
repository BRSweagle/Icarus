pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        git(url: 'https://github.com/BRSweagle/Icarus', poll: true)
      }
    }

    stage('Config') {
      steps {
        SWEAGLEUpload(actionName: 'uploadConfig', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus,Components,Files', tag: '${BUILD_ID)', withSnapshot: true)
      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }

  }
}