pipeline {
            agent any
            stages {

              stage('Retrieve Sources') {
                steps {
                  echo workspace
                  git branch: 'master',
                     url: 'https://github.com/BRSweagle/Icarus'
            	  }
              }

    stage('Config') {
      steps {
        SWEAGLEUpload(actionName: 'uploadProp', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadJSON', fileLocation: 'Components/Microservices/*.json', format: 'JSON', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadYAML', fileLocation: 'Components/Microservices/*.yaml', format: 'yaml', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
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
