pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        git(url: 'https://github.com/BRSweagle/Icarus', poll: true, branch: 'main')
      }
    }

    stage('Config') {
      steps {
        SWEAGLEUpload(actionName: 'uploadProps', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus,Components,Files', showResults: true, withSnapshot: true, tag: '${BUILD_ID}')
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