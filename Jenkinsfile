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
        SWEAGLEUpload(actionName: 'uploadProps', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus,Components,Files', showResults: true)
        SWEAGLEUpload(actionName: 'uploadJSON', fileLocation: 'Components,Microservices,*json', format: 'JSON', nodePath: 'Icarus,Components,Microservices', withSnapshot: true, tag: '${BUILD_ID}', showResults: true)
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