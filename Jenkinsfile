pipeline {
        agent any
        stages {
             stage('Retrieve Sources') {
                  steps {
             echo workspace
             git url: 'https://github.com/BRSweagle/Icarus'
             sh "ls -la"
        }}


    stage('Config') {
      steps {
        SWEAGLEUpload(actionName: 'uploadProps', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus,Components,Files', showResults: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadJSON', fileLocation: 'Components/Microservices/*.json', format: 'JSON', nodePath: 'Icarus,Components,Microservices', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadYAML', fileLocation: 'Components/Microservices/*.yaml', format: 'yaml', nodePath: 'Icarus,Components,Microservices', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
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
